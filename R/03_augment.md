---
title: "03_augment"
format: html
editor: visual
---

## Load clean data


```r
data <- read_tsv(file = "../data/02_dat_clean.tsv")
```

```
## Rows: 158 Columns: 99
## ── Column specification ────────────────────────────────────────────────────────────────────────────────────────────
## Delimiter: "\t"
## chr (30): Age_range, Basic_diseases, Symptoms, Fever_days, IL-6[pg/mL], Oxygenation_index_D1[mmHg], Lactic_acid_...
## dbl (69): Number, Age_over_65(1,YES;_2,_NO), Charlson_index[score], Disease_onset_D1_highest_body_temperature[℃]...
## 
## ℹ Use `spec()` to retrieve the full column specification for this data.
## ℹ Specify the column types or set `show_col_types = FALSE` to quiet this message.
```

Change the ages ranges from 5-years to 10-years


```r
data <- data |> 
    mutate(`Age_range` = case_when(
    str_detect(`Age_range`, "^[0-5][0-9]-") ~ "<60",
    str_detect(`Age_range`, "^6") ~ "60-70",
    str_detect(`Age_range`, "^7") ~ "70-80",
    str_detect(`Age_range`, "^8") ~ "80-90",
    str_detect(`Age_range`, "^9") ~ ">90",
    str_detect(`Age_range`, "^100") ~ ">90"
  )) |> 
  mutate(`Age_range` = fct_relevel(`Age_range`, "<60", "60-70", "70-80", "80-90", ">90"))
```

Create function to change dirty columns with multiple values to clean binary columns


```r
process_dirty_cols <- function(data, column, rename_map) {
  column_sym <- ensym(column)
  
  data_processed <- data |> 
    mutate(
      !!column_sym := str_replace_all(!!column_sym, "([^a-zA-Z()]*).*", "\\1")
    ) |>  
    # Crear varias filas para cada valor en la columna separada por comas o signos +
    separate_rows({{ column }}, sep = "[,+]") |> 
    # Asegurarse de que los valores sean numéricos, asignando 0 si no lo son
    mutate({{ column }} := as.numeric({{ column }})) |> 
    # Expandir las filas a columnas con indicadores binarios
    pivot_wider(
      names_from = {{ column }}, 
      names_prefix = "temp_prefix_",
      values_from = {{ column }}, 
      values_fn = ~1, 
      values_fill = 0
    )
  
  # Si la columna 'temp_prefix_NA' existe, filtrar sus valores
  if ("temp_prefix_NA" %in% names(data_processed)) {
    data_processed <- data_processed |> 
      mutate(across(starts_with("temp_prefix_"), ~if_else(temp_prefix_NA == 1, NA, .))) |> 
      select(-any_of(c("temp_prefix_NA", "temp_prefix_0")))
  } else {
    # Si no existe, simplemente eliminamos la columna 'temp_prefix_0' (si está presente)
    data_processed <- data_processed |> 
      select(-any_of(c("temp_prefix_0")))
  }
  
  # Renombrar columnas según el mapa proporcionado
  data_processed <- data_processed |> 
    rename_with(
      ~gsub(paste0("^", "temp_prefix_"), "", .),  # Elimina el prefijo "temp_prefix_" si está presente
      starts_with("temp_prefix_")
    ) |> 
    rename_with(~ case_when(
      . %in% names(rename_map) ~ rename_map[.],
      TRUE ~ .
    ), everything())
  
  return(data_processed)
}
```

Change the dirty columns


```r
#Basic_disease column
rename_map <- c(
  "1" = "Hypertension_disease",
  "2" = "Diabetes_disease",
  "3" = "CVD_disease",
  "4" = "Cerebrovascular_disease",
  "5" = "COPD_disease",
  "6" = "Immunodeficiency_disease",
  "7" = "Malignant_tumor_disease",
  "8" = "Other_disease",
  "9" = "Chronic_Kidney_disease"
)
data <- process_dirty_cols(data, Basic_diseases, rename_map)

#Symptoms column
rename_map <- c(
  "1" = "Whole_body_symptoms",
  "2" = "Respiratory_symptoms",
  "3" = "Nervous_symptoms",
  "4" = "Cardiovascular_symptoms",
  "5" = "Gastrointestinal_symptoms",
  "6" = "Other_symptoms"
)
data <- process_dirty_cols(data, Symptoms, rename_map)

#D1_oxygen_therapy_mode
rename_map <- c(
  "1" = "Mask_Oxygen_therapy",
  "2" = "NonInvasive_Oxygen_therapy",
  "3" = "HighFlow_Oxygen_therapy",
  "4" = "Invasive_Oxygen_therapy",
  "5" = "ECMO"
)
data <- process_dirty_cols(data, D1_oxygen_therapy_mode, rename_map)

#Bleeding_events
rename_map <- c(
  "0" = "Bleeding_event_none",
  "1" = "Digestive_track",
  "2" = "Bleeding_event_Respiratory_track",
  "3" = "Bleeding_event_Skin",
  "4" = "Bleeding_event_Other")
data <- process_dirty_cols(data, Bleeding_events, rename_map)
```

Change numeric values for words values


```r
data <- data |> 
  mutate(`Antiviral_Drug` = case_when(
    `Antiviral_Drug` == 0 ~ "None",
    `Antiviral_Drug` == 1 ~ "Paxlovid",
    `Antiviral_Drug` == 2 ~ "Azduvine",
    `Antiviral_Drug` == 3 ~ "Other",
    TRUE ~ NA_character_
  )) |> 
    mutate(`Administration_method` = case_when(
    `Administration_method` == 1 ~ "Oral feeding",
    `Administration_method` == 2 ~ "Nasal Feeding",
    TRUE ~ NA_character_
  )) |>
    mutate(`Hormones` = case_when(
    `Hormones` == 1 ~ "Methylprednisolone",
    `Hormones` == 2 ~ "Dexamethasone",
    `Hormones` == 3 ~ "Other",
    TRUE ~ NA_character_
  )) |>
  mutate(`Immunotherapy` = case_when(
    `Immunotherapy` == 1 ~ "Tocilizumab",
    `Immunotherapy` == 2 ~ "Baricitinib",
    `Immunotherapy` == 0 ~ "None",
    TRUE ~ NA_character_
  ))
```

Pulishing binary values (0-1, 1-2 and yes-no)


```r
data <- data |> 
  mutate(`Death` = case_when( 
    `Death` == 1 ~ "1",
    `Death` == 2 ~ "0",
    TRUE ~ NA_character_
  )) |> 
  mutate(`Prone_position_ventilation` = case_when(
    `Prone_position_ventilation` == 1 ~ "yes",
    `Prone_position_ventilation` == 0 ~ "no",
    TRUE ~ NA_character_
  )) |> 
  mutate(`Antibiotics` = case_when(
    `Antibiotics` == 1 ~ "yes",
    `Antibiotics` == 2 ~ "no",
    TRUE ~ NA_character_
  )) |> 
  mutate(`Imaging_Improvement>25%_(after_1_week)` = case_when(
    `Imaging_Improvement>25%_(after_1_week)` == 1 ~ "yes",
    `Imaging_Improvement>25%_(after_1_week)` == 2 ~ "no",
    TRUE ~ NA_character_
  )) |> 
  mutate(`Negative_conversion` = case_when(
    `Negative_conversion` == 1 ~ "yes",
    `Negative_conversion` == 0 ~ "no",
    TRUE ~ NA_character_
  ))
```

### Create Early/Late onset group based on D1 Fever


```r
data <- data |> 
  mutate(onset = case_when(
    `Disease_onset_D1_highest_body_temperature[℃]` > 37.5 ~ "Early",
    TRUE ~ "Late"
  ))
```

### Sum of Basic_Diseases


```r
data <- data |> 
  mutate(Comorbidities_sum = rowSums(select(data, Hypertension_disease : Other_disease)))
```

### Save files


```r
# Save the data as a TSV file
clean_dir <- "../data"
tsv_file <- file.path(clean_dir, "03_data_augmented.tsv")

# Check if the directory exists, create it if not
if (!dir.exists(clean_dir)) {
  dir.create(clean_dir, recursive = TRUE) 
}
#write tsv data
write.table(data, file = tsv_file, sep = "\t", row.names = FALSE)
```