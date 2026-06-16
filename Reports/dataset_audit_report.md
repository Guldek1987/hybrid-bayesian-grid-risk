# Dataset Audit Report

## Dataset Source
- Zenodo record: https://zenodo.org/records/13378476
- Files used in this executable protocol: europe_network.json, loads_2020.zip, gens_2020.zip, lines_2020.zip
- Multi-year extension: disabled in this run because the 2020 archives are already large and contain four matched scenario suffix groups.

## File Audit
                                file  kind  year suffix  rows  columns  sample_missing_values  sample_min  sample_max  sample_mean  size_bytes
  Data/Raw/gens_2020/gens_2020_1.csv  gens  2020      1  8736      815                      0    0.000000   50.880001     2.634456    82483939
  Data/Raw/gens_2020/gens_2020_2.csv  gens  2020      2  8736      815                      0    0.000000   50.880001     2.632504    81981984
  Data/Raw/gens_2020/gens_2020_3.csv  gens  2020      3  8736      815                      0    0.000000   50.880001     2.631701    82192788
  Data/Raw/gens_2020/gens_2020_4.csv  gens  2020      4  8736      815                      0    0.000000   50.880001     2.623322    82059521
Data/Raw/lines_2020/lines_2020_1.csv lines  2020      1  8736     8375                      0  -26.210764   22.319695    -0.006071  1444399165
Data/Raw/lines_2020/lines_2020_2.csv lines  2020      2  8736     8375                      0  -25.709927   22.709206    -0.005338  1444327857
Data/Raw/lines_2020/lines_2020_3.csv lines  2020      3  8736     8375                      0  -25.698883   24.252686    -0.005822  1444369322
Data/Raw/lines_2020/lines_2020_4.csv lines  2020      4  8736     8375                      0  -23.815607   20.661716    -0.005031  1444411447
Data/Raw/loads_2020/loads_2020_1.csv loads  2020      1  8736     4097                      0   -0.127071    6.868115     0.524062   695438289
Data/Raw/loads_2020/loads_2020_2.csv loads  2020      2  8736     4097                      0   -0.199130    6.849415     0.523674   695428141
Data/Raw/loads_2020/loads_2020_3.csv loads  2020      3  8736     4097                      0   -0.038108    7.149072     0.523514   695437418
Data/Raw/loads_2020/loads_2020_4.csv loads  2020      4  8736     4097                      0   -0.057050    6.788832     0.521847   695437350

## Matched Groups
 year suffix  gens  lines  loads  matched_load_gen_line_group
 2020      1     1      1      1                         True
 2020      2     1      1      1                         True
 2020      3     1      1      1                         True
 2020      4     1      1      1                         True

## Network Components
           component  count
                 bus 4097.0
              branch 8375.0
                 gen  815.0
                load 4097.0
              dcline    0.0
             storage    0.0
              switch    0.0
               shunt    0.0
   branch_rate_a_min    1.4
branch_rate_a_median    4.9
   branch_rate_a_max   54.0
generator_type_count   27.0
       country_count   26.0

## Leakage Controls
                 risk                                                                                                     control
Future target leakage Future line-flow targets are produced by group-wise forward shifts after sorting by suffix, line, and time.
    Threshold leakage                                         Risk thresholds and critical-line selection use training rows only.
     Temporal leakage                                                Lag and rolling features use shifted historical values only.
External-test leakage            Suffix group 4 is never used for fitting, calibration, feature selection, or ablation decisions.
          Test tuning                          Only validation data are used for hyperparameter and decision-threshold selection.
