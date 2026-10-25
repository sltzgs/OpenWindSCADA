# OpenWindSCADA


### Repository of openly available wind turbine SCADA datasets with high-level descriptions, reusable data loaders for convenient CSV import, and a platform for documenting insights related to data quality and malfunctions.

For questions and feedback, plese reach out to: simon.leszek@tu-berlin.de

## Table of open source wind turbine SCADA data sets:


|   |ID| Dataset                                                                                                        | .jpynb                                     |Loc        |Met-<br>mast   |Trb<br>#   |Var<br>#   |Logs<br>&check;/&cross;  |Labels<br>&check;/&cross;           |&Delta;T   |&sum;T       |Ref | Remarks/License  |
|---|--|----------------------------------------------------------------------------------------------------------------|--------------------------------------------|-          |-              |-      |-      |-      |-                     |-          |-             | -  |--------------------------------------------|
| |1 | [EDP Open Data](https://www.edp.com/en/innovation/open-data/data)                                              | [here](notebooks/edp_open_data.ipynb)      | ESP (on)  |&check;        | 5     |~80    | &check;     | &check;<sup>[1](#fn1)</sup>| 10m     | 2y |  - | :warning: Original source unavailable; T09 removed from dataset; re-hosted [mirror](https://data.mendeley.com/datasets/zjxjnjp3xs/1) (8 xlsx; T01/T06/T07/T11; SCADA ~417k&times;83, met-mast ~87.5k&times;41, logs ~256k rows; T09 also absent) - check licensing of the 3rd-party re-upload; [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/) |
| |2 | [Winji Gearbox Challenge](https://www.wedowind.ch/blog/winji-register)                                         | &cross;                                    | ?         |?              | 5     |~20    | &check;     | &check;<sup>[2](#fn2)</sup>| 10m     | 3y |  - |  register & consent from WinJi | 
|:star:|3 | [Kelmarsh Farm](https://zenodo.org/records/16807551)                                                           | [here](notebooks/kelmarsh_open_data.ipynb) | UK (on)   |&cross;        | 6     |~99     | &check;     | &cross;                    | 10m<sup>[3](#fn3)</sup>     | 9y|  - | 6&times; Senvion MM92, 2016-2024 (v2025 supersedes the [older record](https://zenodo.org/record/5841834), 5y); via Greenbyte; [farm info](https://www.thewindpower.net/windfarm_en_17507_kelmarsh.php); [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/) (Cubico)|
|:star:|4 | [Penmanshiel Farm](https://zenodo.org/records/16807304)                                                        | &cross;                                    | UK (on)   |&cross;        |14     |>150     | &check;     | &cross;                   | 10m<sup>[3](#fn3)</sup>     | 9y|  - | 14&times; Senvion MM82, 2016-2024 (v3 supersedes the [older record](https://zenodo.org/record/5946808), 5y); WT03 absent; via Greenbyte; incl. substation/PMU meter (2023-24) & fiscal/grid meter; [farm info](https://www.thewindpower.net/windfarm_en_23147_penmanshiel.php); [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/) (Cubico) |
| |5 | [Ørsted Anholt Offshore](https://orsted.com/en/our-business/offshore-wind/offshore-operational-data)           | &cross;                                    | DEN (off) |(&check;)<sup>[4](#fn4)</sup>       | 111  | ?     | ?     | ?                    | 10m     | 2y           |  - | application/NDA; [farm info](https://www.thewindpower.net/windfarm_en_10687_anholt.php) |
| |6 | [Ørsted Westermost Rough](https://orsted.com/en/our-business/offshore-wind/offshore-operational-data)          | &cross;                                    | UK (off)  |(&check;)<sup>[4](#fn4)</sup>       | 35   | ?     | ?     | ?                    | 10m     | 2y           |  - | application/NDA; [farm info](https://www.thewindpower.net/windfarm_en_21826_westermost-rough.php) | 
| |7a| ["CAREtoCompare" Windfarm B](https://data.niaid.nih.gov/resources?id=zenodo_10958774)                          | &cross;                                    | GER (off) |?       | 9    |  64| ?     | &check;                    | 10m     | 2y           |  - | normalized for anonymization; v6 (07/2025) corrected labels; :warning: use Avg signals only - Min/Max/Std unreliable (see Zenodo data-quality note) |
| |7b| ["CAREtoCompare" Windfarm C](https://data.niaid.nih.gov/resources?id=zenodo_10958774)                          | &cross;                                    | GER (off) |?       | 22   | 238| ?     | &check;                  | 10m     | 2y          |  - | normalized for anonymization; v6 (07/2025) corrected labels |
| |8 | [Fuhrländer Farm](https://github.com/alecuba16/fuhrlander)                                                     | &cross;                                    | ? (on)    |&cross;        | 5   | 312| &check;     | &cross;                  | 5m     | 3y          |  [[2]](#ref2) | Eclipse Public License v2.0 |
| |9a | [DSforWind Windfarm 1a](https://zenodo.org/records/5516552)                                                   | &cross;                                    | ? (on)    |&check;<sup>[6](#fn6)</sup>| 4     | 7     | &cross;     | &cross;      | 10m     | 1y           |  - | - |
| |9b | [DSforWind Windfarm1b](https://zenodo.org/records/5516552)                                                    | &cross;                                    | ? (off)   |&check;<sup>[6](#fn6)</sup>| 2     | 7     | &cross;     | &cross;      | 10m     | 1y           |  - | - | 
| |9c | [DSforWind Windfarm 2a](https://zenodo.org/records/5516554)                                                   | &cross;                                    | ? (on)    |&check;<sup>[6](#fn6)</sup>| 2     | 7     | &cross;     | &cross;      | 10m     | 1y           |  - | - | 
| |9d | [DSforWind Windfarm 2b](https://zenodo.org/records/5516554)                                                   | &cross;                                    | ? (off)   |&check;<sup>[6](#fn6)</sup>| 2     | 7     | &cross;     | &cross;      | 10m     | 1y           |  - | - | 
| |10 | [PCWG Data Sets](https://pcwg.org/)                                                                           | &cross;                                    | ? (on)    |&check;        | 3     | 1     | &cross;     | &cross;                   | 10m         | 1y       |  - | - |
| |11a | [Norrekaer Windfarm](https://data.dtu.dk/articles/dataset/SCADA_data_from_Norre_m2_wind_farm/19076756)        | &cross;                                    | DK (on)   |&check;        | 41     | 3     | &cross;     | &cross;                   | 10m         | 1.5y       |  [[3]](#ref3) | [farm info](https://gitlab.windenergy.dtu.dk/fair-data/winddata-revamp/winddata-documentation/-/blob/master/norre_m2.md) |
| |11b | [Delabole Windfarm](https://data.dtu.dk/articles/dataset/Scada_data_from_Delabole_wind_farm/14077004)         | &cross;                                    | UK (on)   |&check;        | 10     | 1     | &cross;     | &cross;                   | 10m         | 1y       |  [[4]](#ref4) | [farm info](https://gitlab.windenergy.dtu.dk/fair-data/winddata-revamp/winddata-documentation/-/blob/master/delabole.md) |
| |12| [Dundalk IoT](https://data.mendeley.com/datasets/tm988rs48k/2)                                                 | &cross;                                    | IRE (on)  |&cross;        | 1     | 20   | &cross;     | &check;<sup>[7](#fn7)</sup>| 10m     | **14y**          |  - | urban terrain |
| |13| [Kaggle Wind Turbine](https://www.kaggle.com/berkerisen/wind-turbine-scada-dataset)                            | &cross;                                    | TUR (on)  |&cross;        | 1     | 4     | &cross;     | &cross;                    | 10m     | 1y|  - | - | 
| |14| [Small São Paulo](https://zenodo.org/records/7348454)                                                          | &cross;                                    | BRZ (on)  |&cross;        | 1     | ~40   | &cross;     | &cross;                        | 1m      | 5y|  - | small, urban turbine | 
| |15| [Björkö Wind Turbine](https://zenodo.org/records/8213270)                                                      | &cross;                                    | SWE (on)  |&cross;        | 1     | 68   | &cross;     | &cross;                        | **1s**      | 1y|  - | small; [turbine info](https://www.chalmers.se/en/departments/e2/resources-and-collaboration/chalmers-wind-turbine/)| 
| |16| [IET-OST Turbine](https://zenodo.org/records/8192149)                                                          | &cross;                                    | SUI (on)  |&cross;        | 1     | 15   | &cross;     | &cross;                        | **1s**      | 1.5y|  - | small; [turbine info](https://www.ost.ch/en/research-and-consulting-services/technology/renewable-energies-and-environmental-engineering/iet-institute-for-energy-technology/wind-energy/infrastructure)| 
| |17| [Pedra do Sal Wind Farm](https://zenodo.org/records/1475197)                                                   | &cross;                                    | BRZ (on)  |&check;        | 20     | ~40   | &cross;     | &cross;                        | 10m      | 1y |  - | [farm info](https://www.thewindpower.net/windfarm_en_15922_pedra-do-sal.php)| 
| |18| [Beberibe Wind Farm](https://zenodo.org/records/1475197)                                                       | &cross;                                    | BRZ (on)  |&check;        | 32     | ~40   | &cross;     | &cross;                        | 10m      | 1y |  - | [farm info](https://www.thewindpower.net/windfarm_en_7032_beberibe.php)| 
| |19| [SMARTEOLE Wind Farm](https://zenodo.org/records/7342466)                                                      | &cross;                                    | FRA (on)  |&check;        | 7     | ~40   | &check;     | &cross;                        | 1m      | 4m |  [[5]](#ref5) | wake steering; [farm info](https://www.thewindpower.net/windfarm_de_3987_sole-du-moulin-vieux.php)| 
| |20| [Loegtved VestasV100](https://www.kaggle.com/datasets/morteneghj/vestas-v100-pitch-power-windspeed/data)      | &cross;                                    | DK (on)  |&cross;        | 1     | 3   | &cross;     | &cross;                        | 10m      | 4y |  - | [contact for more data](https://www.linkedin.com/in/mortenvanggaard)| 
| |21 | [Hill of Towie Wind Farm Open Dataset](https://zenodo.org/records/14870023)                                  | &cross;                                    | [SCT (on)](https://maps.app.goo.gl/e8H1enJBV1pAQqCi8) |&cross;        | 21        |**655**       | &check;                    | &cross;                            | 10m       | 8.7y        | -   | CC-BY-4.0; AeroUp/TuneUp upgrade info included, data loader [here](https://github.com/resgroup/hill-of-towie-open-source-analysis) |
| |22 | [Baltic Coast Siemens 2MW Drivetrain](https://data.mendeley.com/datasets/3sys4562ny/2)                        | &cross;                                    | POL (on)  |&cross;        | 1         |12            | &cross;                    | &check;<sup>[8](#fn8)</sup>        | 10m       | 30d         | -   | CC BY 4.0; drivetrain focus (gearbox/generator temperatures); [DOI](https://doi.org/10.17632/3sys4562ny.2) |
|:new::exclamation:|23 | [SDWPF (Baidu KDD Cup 2022)](https://figshare.com/articles/dataset/SDWPF_dataset/24798654)                      | &cross;                                    | CHN (?)   |&cross;        | **134**   |10            | &cross;                    | &cross;                            | 10m       | 2y          | [[6]](#ref6) | Longyuan Power; turbine coordinates & elevation incl.; `sdwpf_full` = 24 months + ERA5 (humidity, wind speed/dir), >11.4M entries; KDD Cup version = 245d subset; [HF mirror](https://huggingface.co/datasets/AI4Climate/WindFarm_raw); CC BY 4.0 |
|:new::exclamation:|24 | [Sotavento Experimental Wind Farm](https://www.sotaventogalicia.com/en/technical-area/real-time-data/historical/)| &cross;                                   | ESP (on)  |&check;        | 24        |3             | &cross;                    | &cross;                            | 10m       | ?           | -   | 9 turbine models from 5 OEMs (Gamesa, Made, Ecotecnia, NegMicon, Bonus), 17.56 MW, operating since 2001; per turbine only power, wind speed & cumulative energy; free use for non-profit purposes + citation of "SOTAVENTO GALICIA, S.A."; more variables on request (datos@sotaventogalicia.com) at a cost |
|:new::exclamation:|25a| [NREL Flatirons GE 1.5MW SLE](https://data.openei.org/submissions/4143)                                        | &cross;                                    | USA (on)  |&check;        | 1         |?             | &cross;                    | &cross;                            | ?         | ?           | -   | :warning: research turbine, not fleet-representative; met mast directly upstream; filtered to wind from 285&deg;&plusmn;15&deg; (noise study); incl. noise spectra & sound pressure at 11 stations; [DOI](https://doi.org/10.21947/1775531); CC BY 4.0 |
|:new::exclamation:|25b| [NREL SUMR-D / CART2](https://data.openei.org/submissions/4189)                                                | &cross;                                    | USA (on)  |&check;        | 1         |?             | &cross;                    | &cross;                            | 5m        | ?           | -   | :warning: research turbine with highly flexible rotor (ARPA-E SUMR-D project); power, loads & met during startup/operation/shutdown/parked/idle; .mat & .xlsx with MATLAB loader scripts; CC BY 4.0 |
| |98| [Engie La Haute Borne](https://opendata-renewables.engie.com/)                                                 | &cross;                                    | FR (on)   |&cross;        | 4     |34<sup>[9](#fn9)</sup>    | &cross;     | &cross;                    | 10m     | 8y| -  |  original portal offline; re-hosted [mirror](https://data.mendeley.com/datasets/vmyg4yp3s8/1) (4&times; Senvion MM82, 2013-01-01 - 2020-12-31, 1,057,868 records, CC BY 4.0; its title misspells the farm as "La Houte Bourne" and locates it in Villeneuve-d'Ascq - the farm is at Vaudeville-le-Haut, Meuse) - check licensing of the 3rd-party re-upload; [farm info](https://www.thewindpower.net/windfarm_en_3354_la-haute-borne-vaudeville-le-haut.php) |
|:-1:|99| [Levenmouth Turbine](https://pod.ore.catapult.org.uk/data-collection/ldt-turbine-scada-10m)                    | &cross;                                    | UK (near) |&check;        | 1     | >500  | &check;     | &cross;                        | 10m/1s| 3y|  - | not for free (~2000 £) |

- &cross; = no / &check; = yes
- :-1: = no longer available
- :star: = comprehensive dataset
- :new::exclamation: = latest addition
- **bold** = best in class

<div id="fn1"><sup>1</sup> Manual annotations of major failures or component replacements </div>
<div id="fn2"><sup>2</sup> SCADA error log indicator</div>
<div id="fn3"><sup>3</sup> Statistics from wave buoy and ground-based LIDAR data.</div>
<div id="fn4"><sup>4</sup> Higher resolution on request</div>
<div id="fn5"><sup>5</sup> Environmental measures (except wind speed & TI) come from metmast </div>
<div id="fn6"><sup>6</sup> Ground-based LIDAR</div>
<div id="fn7"><sup>7</sup> Gearbox replacement in 2018-2019 </div>
<div id="fn8"><sup>8</sup> Single annotated gearbox bearing failure on 2012-11-09 13:00 (sample 1232)</div>
<div id="fn9"><sup>9</sup> 34 process parameters, each with avg/std/max/min per interval (~136 columns)</div>

## Notebooks - Data Loaders and Overview Plots:
The jupyter notebooks in the 'notebooks' folder contain a data loader for SCADA signals, logs, annotations as well as community annotations (see next sections). Table 1 indicates whether the respective dataset has already been added. Furthermore, they produce an overview over each dataset such as shown in the following image:

![image](./images/data_overview_example.png)

Also, for each turbine, there is an 'Overview Cockpit' with a power curve plot, a wind rose and the data avilability over time. An example is shown here:

![image](./images/turbine_cockpit_example.png)

Lastly, operator annotations are listed, if they are part of the dataset. See e.g. for T01 of the edp data set:

![image](./images/operator_annotations_example.png)

To run the notebooks yourself, please add the respective .csv-files to the data folder.

## Comunity Annotations:
We want to enable researchers to build upon the findings of others who were previously working with the dataset. For every dataset, we have set up a [community-annotation folder](./communiy_annotations), containing simple CSV's to collect data quality or malfunction related observations. They contain the following columns:

- annot_id: unique annotation identifies (running ascending number) 
- turbine_id: which turbine of the respective dataset is affected?
- signal: which signal exhibits the respective observation?
- time_start / time_stop: during which time is the observation present?
- related_log_message (optional): is there a SCADA log message that coincides with the observation?
- remarks: describe your observation in a few words.

The respective notebooks automatically load, read and display the respective malfuncitons. See e.g. this example from T01 of the edp-dataset:

![image](./images/community_annotations_example.png)

## How to contribute:
We welcome contributions to expand the collection of open datasets in this repository as well as community annotations for the datasets. Feel free to create respective PRs :).

## Other Resources:
- [IEA Task 43](https://iea-wind.org/task43/task-43-open-data/)

## References:
Many of the above listed datasets are described and analysed in [[1]](#ref1).

<div id="ref1">[1]</div>[Effenberger, Nina, and Nicole Ludwig. "A collection and categorization of open‐source wind and wind power datasets." Wind Energy 25.10 (2022): 1659-1683.](https://onlinelibrary.wiley.com/doi/full/10.1002/we.2766)

<div id="ref2">[2]</div>[Marti-Puig, P., Blanco-M., A., Cusidó, J. et al. Wind turbine database for intelligent operation and maintenance strategies. Sci Data 11, 255 (2024).](https://www.nature.com/articles/s41597-024-03067-9)

<div id="ref3">[3]</div>[Hansen, Kurt Schaldemose; Vasiljevic, Nikola; Sørensen, Steen Arne (2022). SCADA data from Norre_m2 wind farm. Technical University of Denmark. Dataset.] (https://doi.org/10.11583/DTU.19076756.v1)

<div id="ref4">[4]</div>[Hansen, Kurt Schaldemose (2021). Scada data from Delabole wind farm. Technical University of Denmark. Dataset.] (https://doi.org/10.11583/DTU.14077004)

<div id="ref5">[5]</div>[Simley, E., Fleming, P., Girard, N., Alloin, L., Godefroy, E., and Duc, T.: Results from a wake-steering experiment at a commercial wind plant: investigating the wind speed dependence of wake-steering performance, Wind Energ. Sci., 6, 1427–1453, 2021.](https://doi.org/10.5194/wes-6-1427-2021)

<div id="ref6">[6]</div>[SDWPF: A Dataset for Spatial Dynamic Wind Power Forecasting over a Large Turbine Array. Scientific Data (2024).](https://www.nature.com/articles/s41597-024-03427-5)

## Usage
![Stargazers over time](https://starchart.cc/sltzgs/OpenWindSCADA.svg)
