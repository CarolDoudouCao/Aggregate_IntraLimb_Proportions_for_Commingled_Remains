# Evaluating an Aggregate Method for Estimating Intra-Limb Proportions for Commingled Remains

This repository contains illustrations, scripts and outcome graphs for evaluating an Aggregate Method for Estimating Intra-Limb Proportions for Commingled Remains.

## Data Availability
Two published datasets were used to create the global dataset analyzed here:
1. Ruff's European dataset (https://fae.johnshopkins.edu/chris-ruff/)
2. The Goldman Osteometric dataset (http://web.utk.edu/~auerbach/GOLD.htm)

## File Organization
The repository includes two directories: `scripts` and `outcome`. 
There is also an additional word document (_'updated_reproducible_code_simulating_aggregated_indices'_) containing the full code for handling the data and corresponding results.

### Scripts
The `scripts` directory contains code for data preparation, method simulation, and result plotting. It is further divided into the following four folders:

- **Prepare, Summarize, and Compare Data**: This folder contains code for pre-processing the data, providing summary statistics, and comparing sex differences in limb lengths across global groups.
- **Correlation Between Aggregate and Conventional Indices**: Here, you can find scripts that explore the correlation between aggregate and conventional indices using linear regression.
- **Simulating Three Commingling Conditions**: This folder contains code for simulating three commingling conditions.
- **Plot Errors**: The scripts in this folder are used for plotting errors associated with the aggregate method in predicting conventional indices under various commingling conditions.

### Outcome
The `outcome` directory includes three folders:

- **Plot Global Data**: This folder contains visualizations of limb lengths and indices (Brachial and Crural indices) in the global dataset.
- **Compare Without Simulating**: Here, you can find visualizations showing the correlation between aggregate and conventional indices without manipulating the commingling conditions.
- **Plot Errors**: This folder includes plots depicting the errors obtained using the aggregate method in predicting the conventional indices under various commingling conditions.
 
## Illustration

The illustration provides a comparison between the conventional approach and the aggregate approach for estimating intra-limb proportions, as well as the description of the simulation parameters

### Conventional and Aggregate Approaches for Estimating Intra-Limb Proportions
The table below compares the conventional approach, where an index is calculated for each individual and then averaged for the group, with the aggregate approach that computes the mean of relevant measurements for an aggregated index. 

| Method                | Conventional Approach                                                                          | Aggregate Approach                                                                      |
|-----------------------|----------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------|
| Description           | Index calculated for each individual, and then mean taken for the group                       | Mean of relevant measurements computed for aggregated index                              |
| BI Equation           | BIi = RMLi / HMLi * 100                                                                       | BIgroup = (Σ(BI) i) / n                                                                  |
| CI Equation           | CIi = TMLi / FBLi * 100                                                                       | CIgroup = (Σ(CIi)) / n                                                                   |
| Applicability         | Suitable for identified individuals                                                           | Practical for commingled remains without identified individuals                          |
| Benefits              | Provides individual- and population-level analysis                                           | Enables comparison between different populations without individual identification      |
| Limitations           | Not feasible for commingled remains                                                           | Validity and comparability to the conventional method of estimating intra-limb proportions require further investigation |
* i: the ith individual in the group; n: the total number of individuals in the group; Σ: the sum from i = 1 to n. BIi: the Brachial Index for the ith individual; CIi: the Crural Index for the ith individual. BIgroup: the Brachial Index on group level; CIgroup: the Crural Index on group level. RMLi: the radial length for the ith individual; HMLi: the humeral length for the ith individual; TMLi: the tibial length for the ith individual; FBLi: the bicondylar femoral length for the ith individual. 

### Description of Arguments in the Simulation
Regarding the arguments in the simulation, the input includes the total number of sample limbs, the number of matched and unmatched bones, commingling degree, mean values, and standard deviations. The output arguments consist of estimated Brachial and Crural Indices, as well as the errors between the estimated and input indices.
#### Input Arguments
| Argument     | Description                                                                             |
|--------------|-----------------------------------------------------------------------------------------|
| N            | The total number of sample limbs, which can be the combination of the humerus and radius for the upper limb, or the combination of the femur and tibiae for the lower limb |
| n1           | The number of matched bones, i.e., humeri and radius (or the femur and tibia) from the same individual |
| n2           | The number of matched bones, i.e., the humerus and radius (or the femur and tibia) from different individuals |
| c            | The commingling degree of sample limbs, which quantifies the proportion of unmatched bones within the assemblage. For example, n2 can be calculated as N * c, while n1 can be calculated as N * (1 - c) |
| mean.hml     | The mean of the maximum humeral length                                                  |
| mean.fbl     | The mean of the bicondylar femoral length                                               |
| mean.bic     | The mean of the conventional Brachial Index                                             |
| mean.cic     | The mean of the conventional Crural Index                                               |
| sd.hml       | The standard deviation of the maximum humeral length                                    |
| sd.fbl       | The standard deviation of the bicondylar femoral length                                 |
| sd.bic       | The standard deviation of the conventional Brachial Index, which also represents the within-group variation in the intra-upper-limb proportion |
| sd.cic       | The standard deviation of the conventional Crural Index, which also represents the within-group variation in the intra-lower-limb proportion |
| nsim         | The number of iterations to be performed in the simulation loop                          |

#### Output Arguments
| Argument     | Description                                                                 |
|--------------|-----------------------------------------------------------------------------|
| est.bi       | Estimated Brachial Index using the aggregate method                          |
| est.ci       | Estimated Crural Index using the aggregate method                            |
| error.bi     | The difference between the estimated Brachial Index and the input Brachial Index, i.e., error.bi = est.bi - mean.bic |
| error.ci     | The difference between the estimated Crural Index and the input Crural Index, i.e., error.ci = est.ci - mean.cic |

## R Session Info
```
R version 4.1.3 (2022-03-10)
  
Below are attached packages:
 [1] ".GlobalEnv"          "package:scales"      "package:gridExtra"   "package:terra"       "package:lubridate"   "package:forcats"    
 [7] "package:stringr"     "package:dplyr"       "package:purrr"       "package:readr"       "package:tidyr"       "package:tibble"     
[13] "package:ggplot2"     "package:tidyverse"   "package:viridis"     "package:viridisLite" "tools:rstudio"       "package:stats"      
[19] "package:graphics"    "package:grDevices"   "package:utils"       "package:datasets"    "package:methods"     "Autoloads"          
[25] "package:base"

```
