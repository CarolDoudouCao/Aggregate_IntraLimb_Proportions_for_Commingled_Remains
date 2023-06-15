# Evaluating an Aggregate Method for Estimating Intra-Limb Proportions for Commingled Remains

This repository contains illustrations and scripts for evaluating an Aggregate Method for Estimating Intra-Limb Proportions for Commingled Remains.

## Data Availability
Two published datasets were used to create the global dataset analyzed here:
1. Ruff's European dataset (https://fae.johnshopkins.edu/chris-ruff/)
2. The Goldman Osteometric dataset (http://web.utk.edu/~auerbach/GOLD.htm)

## File Organization
The repository includes two directories: `scripts` and `outcome`.

### Scripts
The `scripts` directory contains code for data preparation, method simulation, and result plotting. It is further divided into the following four folders:

- **Prepare, Summarize, and Compare Data**: This folder contains code for pre-processing the data, providing summary statistics, and comparing sex differences in limb lengths across global groups.
- **Correlation Between Aggregate and Conventional Indices**: Here, you can find scripts that explore the correlation between aggregate and conventional indices.
- **Simulating Three Commingling Conditions**: This folder contains code for simulating three commingling conditions.
- **Plot Errors**: The scripts in this folder are used for plotting errors associated with the aggregate method in predicting conventional indices under various commingling conditions.

### Outcome
The `outcome` directory includes three folders:

- **Plot Global Data**: This folder contains visualizations of limb lengths and indices (Brachial and Crural indices) in the global dataset.
- **Compare Without Simulating**: Here, you can find visualizations showing the correlation between aggregate and conventional indices without manipulating the commingling conditions.
- **Plot Errors**: This folder includes plots depicting the errors obtained using the aggregate method in predicting the conventional indices under various commingling conditions.


## R Session Info
```
R version 4.1.3 (2022-03-10)
  
attached base packages:
 [1] ".GlobalEnv"          "package:scales"      "package:gridExtra"   "package:terra"       "package:lubridate"   "package:forcats"    
 [7] "package:stringr"     "package:dplyr"       "package:purrr"       "package:readr"       "package:tidyr"       "package:tibble"     
[13] "package:ggplot2"     "package:tidyverse"   "package:viridis"     "package:viridisLite" "tools:rstudio"       "package:stats"      
[19] "package:graphics"    "package:grDevices"   "package:utils"       "package:datasets"    "package:methods"     "Autoloads"          
[25] "package:base"

```
