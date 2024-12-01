---
title: "04_describe"
format: html
editor: visual
---

## Load augmented data

::: {.cell}

:::

::: {.cell}

:::

### Change from binary to No, Yes and the labels in the tables

::: {.cell}

:::

## Exclude NA values from tables

::: {.cell}

:::

### Age group, Hospitalization time and ICU hospitalization days by outcome

::: {.cell}
::: {.cell-output .cell-output-stdout}

```
<table class="Rtable1">
<thead>
<tr>
<th class='rowlabel firstrow lastrow'></th>
<th class='firstrow lastrow'><span class='stratlabel'>Deceased<br><span class='stratn'>(N=78)</span></span></th>
<th class='firstrow lastrow'><span class='stratlabel'>Survived<br><span class='stratn'>(N=80)</span></span></th>
<th class='firstrow lastrow'><span class='stratlabel'>Overall<br><span class='stratn'>(N=158)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td class='rowlabel firstrow'>Age Group (Years)</td>
<td class='firstrow'></td>
<td class='firstrow'></td>
<td class='firstrow'></td>
</tr>
<tr>
<td class='rowlabel'><60</td>
<td>6 (7.7%)</td>
<td>7 (8.8%)</td>
<td>13 (8.2%)</td>
</tr>
<tr>
<td class='rowlabel'>>90</td>
<td>16 (20.5%)</td>
<td>4 (5.0%)</td>
<td>20 (12.7%)</td>
</tr>
<tr>
<td class='rowlabel'>60-70</td>
<td>7 (9.0%)</td>
<td>21 (26.3%)</td>
<td>28 (17.7%)</td>
</tr>
<tr>
<td class='rowlabel'>70-80</td>
<td>12 (15.4%)</td>
<td>21 (26.3%)</td>
<td>33 (20.9%)</td>
</tr>
<tr>
<td class='rowlabel lastrow'>80-90</td>
<td class='lastrow'>37 (47.4%)</td>
<td class='lastrow'>27 (33.8%)</td>
<td class='lastrow'>64 (40.5%)</td>
</tr>
<tr>
<td class='rowlabel firstrow'>Hospitalization Time (Days)</td>
<td class='firstrow'></td>
<td class='firstrow'></td>
<td class='firstrow'></td>
</tr>
<tr>
<td class='rowlabel'>Mean (SD)</td>
<td>12.8 (8.74)</td>
<td>16.0 (11.3)</td>
<td>14.4 (10.2)</td>
</tr>
<tr>
<td class='rowlabel lastrow'>Median [Min, Max]</td>
<td class='lastrow'>10.0 [2.00, 41.0]</td>
<td class='lastrow'>12.0 [3.00, 51.0]</td>
<td class='lastrow'>11.0 [2.00, 51.0]</td>
</tr>
<tr>
<td class='rowlabel firstrow'>ICU_hospitalization_days</td>
<td class='firstrow'></td>
<td class='firstrow'></td>
<td class='firstrow'></td>
</tr>
<tr>
<td class='rowlabel'>Mean (SD)</td>
<td>9.62 (9.28)</td>
<td>3.81 (8.13)</td>
<td>6.77 (9.18)</td>
</tr>
<tr>
<td class='rowlabel'>Median [Min, Max]</td>
<td>7.00 [0, 41.0]</td>
<td>0 [0, 41.0]</td>
<td>3.00 [0, 41.0]</td>
</tr>
<tr>
<td class='rowlabel lastrow'>Missing</td>
<td class='lastrow'>0 (0%)</td>
<td class='lastrow'>5 (6.3%)</td>
<td class='lastrow'>5 (3.2%)</td>
</tr>
</tbody>
</table>
```


:::

::: {.cell-output .cell-output-stdout}

```
png 
  2 
```


:::
:::

### Diseases by outcome

::: {.cell}
::: {.cell-output-display}

```{=html}
<div class="Rtable1"><table class="Rtable1">
<thead>
<tr>
<th class='rowlabel firstrow lastrow'></th>
<th class='firstrow lastrow'><span class='stratlabel'>Deceased<br><span class='stratn'>(N=78)</span></span></th>
<th class='firstrow lastrow'><span class='stratlabel'>Survived<br><span class='stratn'>(N=80)</span></span></th>
<th class='firstrow lastrow'><span class='stratlabel'>Overall<br><span class='stratn'>(N=158)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td class='rowlabel firstrow'>Hypertension_disease</td>
<td class='firstrow'></td>
<td class='firstrow'></td>
<td class='firstrow'></td>
</tr>
<tr>
<td class='rowlabel'>No</td>
<td>17 (21.8%)</td>
<td>32 (40.0%)</td>
<td>49 (31.0%)</td>
</tr>
<tr>
<td class='rowlabel lastrow'>Yes</td>
<td class='lastrow'>55 (70.5%)</td>
<td class='lastrow'>44 (55.0%)</td>
<td class='lastrow'>99 (62.7%)</td>
</tr>
<tr>
<td class='rowlabel firstrow'>Diabetes_disease</td>
<td class='firstrow'></td>
<td class='firstrow'></td>
<td class='firstrow'></td>
</tr>
<tr>
<td class='rowlabel'>No</td>
<td>46 (59.0%)</td>
<td>50 (62.5%)</td>
<td>96 (60.8%)</td>
</tr>
<tr>
<td class='rowlabel lastrow'>Yes</td>
<td class='lastrow'>26 (33.3%)</td>
<td class='lastrow'>26 (32.5%)</td>
<td class='lastrow'>52 (32.9%)</td>
</tr>
<tr>
<td class='rowlabel firstrow'>CVD_disease</td>
<td class='firstrow'></td>
<td class='firstrow'></td>
<td class='firstrow'></td>
</tr>
<tr>
<td class='rowlabel'>No</td>
<td>35 (44.9%)</td>
<td>51 (63.8%)</td>
<td>86 (54.4%)</td>
</tr>
<tr>
<td class='rowlabel lastrow'>Yes</td>
<td class='lastrow'>37 (47.4%)</td>
<td class='lastrow'>25 (31.3%)</td>
<td class='lastrow'>62 (39.2%)</td>
</tr>
<tr>
<td class='rowlabel firstrow'>COPD_disease</td>
<td class='firstrow'></td>
<td class='firstrow'></td>
<td class='firstrow'></td>
</tr>
<tr>
<td class='rowlabel'>No</td>
<td>61 (78.2%)</td>
<td>70 (87.5%)</td>
<td>131 (82.9%)</td>
</tr>
<tr>
<td class='rowlabel lastrow'>Yes</td>
<td class='lastrow'>11 (14.1%)</td>
<td class='lastrow'>6 (7.5%)</td>
<td class='lastrow'>17 (10.8%)</td>
</tr>
<tr>
<td class='rowlabel firstrow'>Cerebrovascular_disease</td>
<td class='firstrow'></td>
<td class='firstrow'></td>
<td class='firstrow'></td>
</tr>
<tr>
<td class='rowlabel'>No</td>
<td>56 (71.8%)</td>
<td>62 (77.5%)</td>
<td>118 (74.7%)</td>
</tr>
<tr>
<td class='rowlabel lastrow'>Yes</td>
<td class='lastrow'>16 (20.5%)</td>
<td class='lastrow'>14 (17.5%)</td>
<td class='lastrow'>30 (19.0%)</td>
</tr>
<tr>
<td class='rowlabel firstrow'>Chronic_Kidney_disease</td>
<td class='firstrow'></td>
<td class='firstrow'></td>
<td class='firstrow'></td>
</tr>
<tr>
<td class='rowlabel'>No</td>
<td>61 (78.2%)</td>
<td>65 (81.3%)</td>
<td>126 (79.7%)</td>
</tr>
<tr>
<td class='rowlabel lastrow'>Yes</td>
<td class='lastrow'>11 (14.1%)</td>
<td class='lastrow'>11 (13.8%)</td>
<td class='lastrow'>22 (13.9%)</td>
</tr>
<tr>
<td class='rowlabel firstrow'>Malignant_tumor_disease</td>
<td class='firstrow'></td>
<td class='firstrow'></td>
<td class='firstrow'></td>
</tr>
<tr>
<td class='rowlabel'>No</td>
<td>66 (84.6%)</td>
<td>62 (77.5%)</td>
<td>128 (81.0%)</td>
</tr>
<tr>
<td class='rowlabel lastrow'>Yes</td>
<td class='lastrow'>6 (7.7%)</td>
<td class='lastrow'>14 (17.5%)</td>
<td class='lastrow'>20 (12.7%)</td>
</tr>
<tr>
<td class='rowlabel firstrow'>Immunodeficiency_disease</td>
<td class='firstrow'></td>
<td class='firstrow'></td>
<td class='firstrow'></td>
</tr>
<tr>
<td class='rowlabel'>No</td>
<td>68 (87.2%)</td>
<td>67 (83.8%)</td>
<td>135 (85.4%)</td>
</tr>
<tr>
<td class='rowlabel lastrow'>Yes</td>
<td class='lastrow'>4 (5.1%)</td>
<td class='lastrow'>9 (11.3%)</td>
<td class='lastrow'>13 (8.2%)</td>
</tr>
<tr>
<td class='rowlabel firstrow'>Other_disease</td>
<td class='firstrow'></td>
<td class='firstrow'></td>
<td class='firstrow'></td>
</tr>
<tr>
<td class='rowlabel'>No</td>
<td>52 (66.7%)</td>
<td>60 (75.0%)</td>
<td>112 (70.9%)</td>
</tr>
<tr>
<td class='rowlabel lastrow'>Yes</td>
<td class='lastrow'>20 (25.6%)</td>
<td class='lastrow'>16 (20.0%)</td>
<td class='lastrow'>36 (22.8%)</td>
</tr>
</tbody>
</table>
</div>
```

:::
:::

### Symptoms by outcome

::: {.cell}
::: {.cell-output-display}

```{=html}
<div class="Rtable1"><table class="Rtable1">
<thead>
<tr>
<th class='rowlabel firstrow lastrow'></th>
<th class='firstrow lastrow'><span class='stratlabel'>Deceased<br><span class='stratn'>(N=78)</span></span></th>
<th class='firstrow lastrow'><span class='stratlabel'>Survived<br><span class='stratn'>(N=80)</span></span></th>
<th class='firstrow lastrow'><span class='stratlabel'>Overall<br><span class='stratn'>(N=158)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td class='rowlabel firstrow'>Whole_body_symptoms</td>
<td class='firstrow'></td>
<td class='firstrow'></td>
<td class='firstrow'></td>
</tr>
<tr>
<td class='rowlabel'>No</td>
<td>9 (11.5%)</td>
<td>7 (8.8%)</td>
<td>16 (10.1%)</td>
</tr>
<tr>
<td class='rowlabel lastrow'>Yes</td>
<td class='lastrow'>67 (85.9%)</td>
<td class='lastrow'>73 (91.3%)</td>
<td class='lastrow'>140 (88.6%)</td>
</tr>
<tr>
<td class='rowlabel firstrow'>Respiratory_symptoms</td>
<td class='firstrow'></td>
<td class='firstrow'></td>
<td class='firstrow'></td>
</tr>
<tr>
<td class='rowlabel'>No</td>
<td>5 (6.4%)</td>
<td>9 (11.3%)</td>
<td>14 (8.9%)</td>
</tr>
<tr>
<td class='rowlabel lastrow'>Yes</td>
<td class='lastrow'>71 (91.0%)</td>
<td class='lastrow'>71 (88.8%)</td>
<td class='lastrow'>142 (89.9%)</td>
</tr>
<tr>
<td class='rowlabel firstrow'>Cardiovascular_symptoms</td>
<td class='firstrow'></td>
<td class='firstrow'></td>
<td class='firstrow'></td>
</tr>
<tr>
<td class='rowlabel'>No</td>
<td>72 (92.3%)</td>
<td>71 (88.8%)</td>
<td>143 (90.5%)</td>
</tr>
<tr>
<td class='rowlabel lastrow'>Yes</td>
<td class='lastrow'>4 (5.1%)</td>
<td class='lastrow'>9 (11.3%)</td>
<td class='lastrow'>13 (8.2%)</td>
</tr>
<tr>
<td class='rowlabel firstrow'>Other_symptoms</td>
<td class='firstrow'></td>
<td class='firstrow'></td>
<td class='firstrow'></td>
</tr>
<tr>
<td class='rowlabel'>No</td>
<td>72 (92.3%)</td>
<td>79 (98.8%)</td>
<td>151 (95.6%)</td>
</tr>
<tr>
<td class='rowlabel lastrow'>Yes</td>
<td class='lastrow'>4 (5.1%)</td>
<td class='lastrow'>1 (1.3%)</td>
<td class='lastrow'>5 (3.2%)</td>
</tr>
<tr>
<td class='rowlabel firstrow'>Nervous_symptoms</td>
<td class='firstrow'></td>
<td class='firstrow'></td>
<td class='firstrow'></td>
</tr>
<tr>
<td class='rowlabel'>No</td>
<td>58 (74.4%)</td>
<td>66 (82.5%)</td>
<td>124 (78.5%)</td>
</tr>
<tr>
<td class='rowlabel lastrow'>Yes</td>
<td class='lastrow'>18 (23.1%)</td>
<td class='lastrow'>14 (17.5%)</td>
<td class='lastrow'>32 (20.3%)</td>
</tr>
<tr>
<td class='rowlabel firstrow'>Gastrointestinal_symptoms</td>
<td class='firstrow'></td>
<td class='firstrow'></td>
<td class='firstrow'></td>
</tr>
<tr>
<td class='rowlabel'>No</td>
<td>66 (84.6%)</td>
<td>75 (93.8%)</td>
<td>141 (89.2%)</td>
</tr>
<tr>
<td class='rowlabel lastrow'>Yes</td>
<td class='lastrow'>10 (12.8%)</td>
<td class='lastrow'>5 (6.3%)</td>
<td class='lastrow'>15 (9.5%)</td>
</tr>
</tbody>
</table>
</div>
```

:::
:::

### Antiviral drug, CTSS, Charlson index score, fever days and onset vs outcome

::: {.cell}
::: {.cell-output-display}

```{=html}
<div class="Rtable1"><table class="Rtable1">
<thead>
<tr>
<th class='rowlabel firstrow lastrow'></th>
<th class='firstrow lastrow'><span class='stratlabel'>Deceased<br><span class='stratn'>(N=78)</span></span></th>
<th class='firstrow lastrow'><span class='stratlabel'>Survived<br><span class='stratn'>(N=80)</span></span></th>
<th class='firstrow lastrow'><span class='stratlabel'>Overall<br><span class='stratn'>(N=158)</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td class='rowlabel firstrow'>Antiviral_Drug</td>
<td class='firstrow'></td>
<td class='firstrow'></td>
<td class='firstrow'></td>
</tr>
<tr>
<td class='rowlabel'>Azduvine</td>
<td>5 (6.4%)</td>
<td>14 (17.5%)</td>
<td>19 (12.0%)</td>
</tr>
<tr>
<td class='rowlabel'>None</td>
<td>17 (21.8%)</td>
<td>10 (12.5%)</td>
<td>27 (17.1%)</td>
</tr>
<tr>
<td class='rowlabel lastrow'>Paxlovid</td>
<td class='lastrow'>50 (64.1%)</td>
<td class='lastrow'>48 (60.0%)</td>
<td class='lastrow'>98 (62.0%)</td>
</tr>
<tr>
<td class='rowlabel firstrow'>CTSS_score_1</td>
<td class='firstrow'></td>
<td class='firstrow'></td>
<td class='firstrow'></td>
</tr>
<tr>
<td class='rowlabel'>Mean (SD)</td>
<td>13.6 (6.00)</td>
<td>12.9 (6.00)</td>
<td>13.2 (5.99)</td>
</tr>
<tr>
<td class='rowlabel'>Median [Min, Max]</td>
<td>12.0 [4.00, 25.0]</td>
<td>12.0 [2.00, 25.0]</td>
<td>12.0 [2.00, 25.0]</td>
</tr>
<tr>
<td class='rowlabel lastrow'>Missing</td>
<td class='lastrow'>11 (14.1%)</td>
<td class='lastrow'>2 (2.5%)</td>
<td class='lastrow'>13 (8.2%)</td>
</tr>
<tr>
<td class='rowlabel firstrow'>CTSS_score_2</td>
<td class='firstrow'></td>
<td class='firstrow'></td>
<td class='firstrow'></td>
</tr>
<tr>
<td class='rowlabel'>Mean (SD)</td>
<td>14.5 (6.28)</td>
<td>11.1 (5.59)</td>
<td>12.3 (6.02)</td>
</tr>
<tr>
<td class='rowlabel'>Median [Min, Max]</td>
<td>13.0 [6.00, 25.0]</td>
<td>10.0 [1.00, 25.0]</td>
<td>11.0 [1.00, 25.0]</td>
</tr>
<tr>
<td class='rowlabel lastrow'>Missing</td>
<td class='lastrow'>42 (53.8%)</td>
<td class='lastrow'>11 (13.8%)</td>
<td class='lastrow'>53 (33.5%)</td>
</tr>
<tr>
<td class='rowlabel firstrow'>Fever_days</td>
<td class='firstrow'></td>
<td class='firstrow'></td>
<td class='firstrow'></td>
</tr>
<tr>
<td class='rowlabel'>Mean (SD)</td>
<td>3.34 (2.46)</td>
<td>1.47 (1.94)</td>
<td>2.39 (2.39)</td>
</tr>
<tr>
<td class='rowlabel'>Median [Min, Max]</td>
<td>3.00 [0, 7.00]</td>
<td>1.00 [0, 7.00]</td>
<td>2.00 [0, 7.00]</td>
</tr>
<tr>
<td class='rowlabel lastrow'>Missing</td>
<td class='lastrow'>25 (32.1%)</td>
<td class='lastrow'>25 (31.3%)</td>
<td class='lastrow'>50 (31.6%)</td>
</tr>
<tr>
<td class='rowlabel firstrow'>Charlson_index[score]</td>
<td class='firstrow'></td>
<td class='firstrow'></td>
<td class='firstrow'></td>
</tr>
<tr>
<td class='rowlabel'>Mean (SD)</td>
<td>5.69 (2.16)</td>
<td>5.24 (2.48)</td>
<td>5.46 (2.33)</td>
</tr>
<tr>
<td class='rowlabel lastrow'>Median [Min, Max]</td>
<td class='lastrow'>5.00 [1.00, 14.0]</td>
<td class='lastrow'>5.00 [0, 14.0]</td>
<td class='lastrow'>5.00 [0, 14.0]</td>
</tr>
<tr>
<td class='rowlabel firstrow'>onset</td>
<td class='firstrow'></td>
<td class='firstrow'></td>
<td class='firstrow'></td>
</tr>
<tr>
<td class='rowlabel'>Early</td>
<td>38 (48.7%)</td>
<td>24 (30.0%)</td>
<td>62 (39.2%)</td>
</tr>
<tr>
<td class='rowlabel lastrow'>Late</td>
<td class='lastrow'>40 (51.3%)</td>
<td class='lastrow'>56 (70.0%)</td>
<td class='lastrow'>96 (60.8%)</td>
</tr>
</tbody>
</table>
</div>
```

:::
:::

### Age group, Symptoms and Diseases by Antiviral Drug

::: {.cell}

:::

### Age group, Symptoms and Diseases by Respiratory support treatments.

::: {.cell}

:::
