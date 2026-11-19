# OpenWindSCADA


### Repository of openly available wind turbine SCADA datasets with high-level descriptions, reusable data loaders for convenient CSV import, and a platform for documenting insights related to data quality and malfunctions.

For questions and feedback, please reach out to: simon.leszek@tu-berlin.de

## Table of open source wind turbine SCADA data sets:

**Legend:** ✅ yes · ❌ no · ? unknown · ⭐ comprehensive dataset · 🆕 latest addition · ⚠️ caveat, see notes · 👎 no longer freely available · **bold** = best in class · **Ref:** [n] = publication introducing the dataset, 📚n = number of listed publications using the dataset (see [Publications](#publications-using-the-datasets)) · 📓 notebook in this repo · ↗️ external loader · on/off/near = onshore/offshore/nearshore · License – = not stated publicly

| ID | Dataset | Loader | Location | Met-mast/<br>LiDAR | Turbines | Vars | Logs | Labels | ΔT | ΣT | Access | License | Ref | Notes |
|----|---------|:------:|----------|:------------------:|---------:|-----:|:----:|:------:|----|----|--------|---------|-----|-------|
| 1 | [EDP Open Data](https://www.edp.com/en/innovation/open-data/data) ⚠️ | [📓](notebooks/edp_open_data.ipynb) | 🇪🇸 on | ✅ | 5 | ~80 | ✅ | ✅[^edp] | 10m | 2y | mirror | [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/) (mirror) | [📚15](#pubs-1) | <details><summary>notes</summary>Original source unavailable; T09 removed from dataset. Re-hosted [mirror](https://data.mendeley.com/datasets/zjxjnjp3xs/1): 8 xlsx files, T01/T06/T07/T11; SCADA ~417k × 83, met-mast ~87.5k × 41, logs ~256k rows; T09 also absent. The mirror is published under CC BY 4.0; the original EDP release was [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/) - check licensing of the 3rd-party re-upload.</details> |
| 2 | [Winji Gearbox Challenge](https://community.wedowind.ch/spaces/17205763/content) | – | ? | ? | 5 | ~20 | ✅ | ✅[^winji] | 10m | 3y | registration | – | [[21]](#ref21) [📚2](#pubs-2) | <details><summary>notes</summary>Requires registration & consent from WinJi.</details> |
| 3 | [Kelmarsh Farm](https://zenodo.org/records/16807551) ⭐ | [📓](notebooks/kelmarsh_open_data.ipynb) | 🇬🇧 on | ❌ | 6 | ~99 | ✅ | ❌ | 10m[^hires] | 9y | open | [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/) | [📚16](#pubs-3) | <details><summary>notes</summary>6 × Senvion MM92, 2016-2024 (v2025 supersedes the [older record](https://zenodo.org/record/5841834), 5y). Via Greenbyte. [Farm info](https://www.thewindpower.net/windfarm_en_17507_kelmarsh.php). [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/) (Cubico).</details> |
| 4 | [Penmanshiel Farm](https://zenodo.org/records/16807304) ⭐ | – | 🇬🇧 on | ❌ | 14 | >150 | ✅ | ❌ | 10m[^hires] | 9y | open | [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/) | [📚21](#pubs-4) | <details><summary>notes</summary>14 × Senvion MM82, 2016-2024 (v3 supersedes the [older record](https://zenodo.org/record/5946808), 5y); WT03 absent. Via Greenbyte. Includes substation/PMU meter (2023-24) & fiscal/grid meter. [Farm info](https://www.thewindpower.net/windfarm_en_23147_penmanshiel.php). [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/) (Cubico).</details> |
| 5 | [Ørsted Anholt Offshore](https://orsted.com/en/our-business/offshore-wind/offshore-operational-data) | – | 🇩🇰 off | (✅)[^buoy] | 111 | ? | ? | ? | 10m | 2y | NDA | – | [📚10](#pubs-5) | <details><summary>notes</summary>Application/NDA required. [Farm info](https://www.thewindpower.net/windfarm_en_10687_anholt.php).</details> |
| 6 | [Ørsted Westermost Rough](https://orsted.com/en/our-business/offshore-wind/offshore-operational-data) | – | 🇬🇧 off | (✅)[^buoy] | 35 | ? | ? | ? | 10m | 2y | NDA | – | [📚7](#pubs-6) | <details><summary>notes</summary>Application/NDA required. [Farm info](https://www.thewindpower.net/windfarm_en_21826_westermost-rough.php).</details> |
| 7a | ["CAREtoCompare" Windfarm B](https://data.niaid.nih.gov/resources?id=zenodo_10958774) ⚠️ | – | 🇩🇪 off | ? | 9 | 64 | ? | ✅ | 10m | 2y | open | [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/) | [[67]](#ref67) [📚13](#pubs-7a-7b) | <details><summary>notes</summary>Normalized for anonymization; v6 (07/2025) corrected labels. ⚠️ Use Avg signals only - Min/Max/Std are unreliable (see Zenodo data-quality note).</details> |
| 7b | ["CAREtoCompare" Windfarm C](https://data.niaid.nih.gov/resources?id=zenodo_10958774) | – | 🇩🇪 off | ? | 22 | 238 | ? | ✅ | 10m | 2y | open | [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/) | [[67]](#ref67) [📚13](#pubs-7a-7b) | <details><summary>notes</summary>Normalized for anonymization; v6 (07/2025) corrected labels.</details> |
| 8 | [Fuhrländer Farm](https://github.com/alecuba16/fuhrlander) | – | ? on | ❌ | 5 | 312 | ✅ | ❌ | 5m | 3y | open | EPL-2.0 | [[80]](#ref80) [📚4](#pubs-8) | <details><summary>notes</summary>Eclipse Public License v2.0.</details> |
| 9a | [DSforWind Windfarm 1a](https://zenodo.org/records/5516552) | – | ? on | ✅[^lidar] | 4 | 7 | ❌ | ❌ | 10m | 1y | open | [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/) | [[84]](#ref84) [📚7](#pubs-9a-9d) | – |
| 9b | [DSforWind Windfarm 1b](https://zenodo.org/records/5516552) | – | ? off | ✅[^lidar] | 2 | 7 | ❌ | ❌ | 10m | 1y | open | [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/) | [[84]](#ref84) [📚7](#pubs-9a-9d) | – |
| 9c | [DSforWind Windfarm 2a](https://zenodo.org/records/5516554) | – | ? on | ✅[^lidar] | 2 | 7 | ❌ | ❌ | 10m | 1y | open | [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/) | [[84]](#ref84) [📚7](#pubs-9a-9d) | – |
| 9d | [DSforWind Windfarm 2b](https://zenodo.org/records/5516554) | – | ? off | ✅[^lidar] | 2 | 7 | ❌ | ❌ | 10m | 1y | open | [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/) | [[84]](#ref84) [📚7](#pubs-9a-9d) | – |
| 10 | [PCWG Data Sets](https://pcwg.org/) | – | ? on | ✅ | 3 | 1 | ❌ | ❌ | 10m | 1y | open | – | [📚1](#pubs-10) | – |
| 11a | [Norrekaer Windfarm](https://data.dtu.dk/articles/dataset/SCADA_data_from_Norre_m2_wind_farm/19076756) | – | 🇩🇰 on | ✅ | 41 | 3 | ❌ | ❌ | 10m | 1.5y | open | [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/) | [📚2](#pubs-11a) | <details><summary>notes</summary>[Dataset DOI](https://doi.org/10.11583/DTU.19076756.v1). [Farm info](https://gitlab.windenergy.dtu.dk/fair-data/winddata-revamp/winddata-documentation/-/blob/master/norre_m2.md).</details> |
| 11b | [Delabole Windfarm](https://data.dtu.dk/articles/dataset/Scada_data_from_Delabole_wind_farm/14077004) | – | 🇬🇧 on | ✅ | 10 | 1 | ❌ | ❌ | 10m | 1y | open | [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/) | - | <details><summary>notes</summary>[Dataset DOI](https://doi.org/10.11583/DTU.14077004). [Farm info](https://gitlab.windenergy.dtu.dk/fair-data/winddata-revamp/winddata-documentation/-/blob/master/delabole.md).</details> |
| 12 | [Dundalk IoT](https://data.mendeley.com/datasets/tm988rs48k/2) | – | 🇮🇪 on | ❌ | 1 | 20 | ❌ | ✅[^dundalk] | 10m | **14y** | open | [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/) | [[94]](#ref94) [📚11](#pubs-12) | <details><summary>notes</summary>Urban terrain.</details> |
| 13 | [Kaggle Wind Turbine](https://www.kaggle.com/berkerisen/wind-turbine-scada-dataset) | – | 🇹🇷 on | ❌ | 1 | 4 | ❌ | ❌ | 10m | 1y | open | not stated (Kaggle: Unknown) | [📚8](#pubs-13) | – |
| 14 | [Small São Paulo](https://zenodo.org/records/7348454) | – | 🇧🇷 on | ❌ | 1 | ~40 | ❌ | ❌ | 1m | 5y | open | [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/) | [[113]](#ref113) [📚3](#pubs-14) | <details><summary>notes</summary>Small, urban turbine.</details> |
| 15 | [Björkö Wind Turbine](https://zenodo.org/records/8213270) | – | 🇸🇪 on | ❌ | 1 | 68 | ❌ | ❌ | **1s** | 1y | open | [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/) | [📚1](#pubs-15) | <details><summary>notes</summary>Small turbine. [Turbine info](https://www.chalmers.se/en/departments/e2/resources-and-collaboration/chalmers-wind-turbine/).</details> |
| 16 | [IET-OST Turbine](https://zenodo.org/records/8192149) | – | 🇨🇭 on | ❌ | 1 | 15 | ❌ | ❌ | **1s** | 1.5y | open | [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/) | [📚4](#pubs-16) | <details><summary>notes</summary>Small turbine. [Turbine info](https://www.ost.ch/en/research-and-consulting-services/technology/renewable-energies-and-environmental-engineering/iet-institute-for-energy-technology/wind-energy/infrastructure).</details> |
| 17 | [Pedra do Sal Wind Farm](https://zenodo.org/records/1475197) | – | 🇧🇷 on | ✅ | 20 | ~40 | ❌ | ❌ | 10m | 1y | open | [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/) | [[121]](#ref121) [📚5](#pubs-17-18) | <details><summary>notes</summary>[Farm info](https://www.thewindpower.net/windfarm_en_15922_pedra-do-sal.php).</details> |
| 18 | [Beberibe Wind Farm](https://zenodo.org/records/1475197) | – | 🇧🇷 on | ✅ | 32 | ~40 | ❌ | ❌ | 10m | 1y | open | [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/) | [[121]](#ref121) [📚5](#pubs-17-18) | <details><summary>notes</summary>[Farm info](https://www.thewindpower.net/windfarm_en_7032_beberibe.php).</details> |
| 19 | [SMARTEOLE Wind Farm](https://zenodo.org/records/7342466) | – | 🇫🇷 on | ✅ | 7 | ~40 | ✅ | ❌ | 1m | 4m | open | [Etalab 2.0](https://www.etalab.gouv.fr/licence-ouverte-open-licence/) | [[125]](#ref125) [📚5](#pubs-19) | <details><summary>notes</summary>Wake steering experiment. [Farm info](https://www.thewindpower.net/windfarm_de_3987_sole-du-moulin-vieux.php).</details> |
| 20 | [Loegtved Vestas V100](https://www.kaggle.com/datasets/morteneghj/vestas-v100-pitch-power-windspeed/data) | – | 🇩🇰 on | ❌ | 1 | 3 | ❌ | ❌ | 10m | 4y | open | Apache 2.0 (as set on Kaggle) | - | <details><summary>notes</summary>[Contact for more data](https://www.linkedin.com/in/mortenvanggaard).</details> |
| 21 | [Hill of Towie Wind Farm](https://doi.org/10.5281/zenodo.14870021) ⭐ | [↗️](https://github.com/resgroup/hill-of-towie-open-source-analysis) | [🇬🇧 on](https://maps.app.goo.gl/e8H1enJBV1pAQqCi8) | ✅[^lidar] | 21 | **700** | ✅ | ❌ | 10m/1s | 10.3y | open | [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/) | [📚5](#pubs-21) | <details><summary>notes</summary>21 × Siemens SWT-2.3-VS-82, 01/2016-04/2026 (v2.1.0 supersedes the [v1 record](https://zenodo.org/records/14870023), 8.7y). Located in Scotland. Includes ~1Hz turbine & Dynamic Yaw controller fastlog data and 10m/high-res ground LiDAR data for 01-04/2026. 700 10m columns in 2026 = 658 turbine + 42 grid-meter (excl. timestamp/ID). Alarm logs & 10m shutdown durations; AeroUp/TuneUp upgrade and Dynamic Yaw (wake steering) campaign info included. Data loader [here](https://github.com/resgroup/hill-of-towie-open-source-analysis). CC-BY-4.0.</details> |
| 22 | [Baltic Coast Siemens 2MW Drivetrain](https://data.mendeley.com/datasets/3sys4562ny/2) | – | 🇵🇱 on | ❌ | 1 | 12 | ❌ | ✅[^bearing] | 10m | 30d | open | [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/) | [[135]](#ref135) [📚5](#pubs-22) | <details><summary>notes</summary>Drivetrain focus (gearbox/generator temperatures). [DOI](https://doi.org/10.17632/3sys4562ny.2). CC BY 4.0.</details> |
| 23 | [SDWPF (Baidu KDD Cup 2022)](https://figshare.com/articles/dataset/SDWPF_dataset/24798654) 🆕 | – | 🇨🇳 ? | ❌ | **134** | 10 | ❌ | ❌ | 10m | 2y | open | [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/) | [[140]](#ref140) [📚10](#pubs-23) | <details><summary>notes</summary>Longyuan Power; turbine coordinates & elevation included. `sdwpf_full` = 24 months + ERA5 (humidity, wind speed/dir), >11.4M entries; KDD Cup version = 245d subset. [HF mirror](https://huggingface.co/datasets/AI4Climate/WindFarm_raw). CC BY 4.0.</details> |
| 24 | [Sotavento Experimental Wind Farm](https://www.sotaventogalicia.com/en/technical-area/real-time-data/historical/) 🆕 | – | 🇪🇸 on | ✅ | 24 | 3 | ❌ | ❌ | 10m | ? | open | non-profit + citation | [📚7](#pubs-24) | <details><summary>notes</summary>9 turbine models from 5 OEMs (Gamesa, Made, Ecotecnia, NegMicon, Bonus), 17.56 MW, operating since 2001. Per turbine only power, wind speed & cumulative energy. Free use for non-profit purposes + citation of "SOTAVENTO GALICIA, S.A."; more variables on request (datos@sotaventogalicia.com) at a cost.</details> |
| 25a | [NREL Flatirons GE 1.5MW SLE](https://data.openei.org/submissions/4143) 🆕 ⚠️ | – | 🇺🇸 on | ✅ | 1 | ? | ❌ | ❌ | ? | ? | open | [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/) | [[156]](#ref156) [📚1](#pubs-25a) | <details><summary>notes</summary>⚠️ Research turbine, not fleet-representative. Met mast directly upstream; filtered to wind from 285° ± 15° (noise study). Includes noise spectra & sound pressure at 11 stations. [DOI](https://doi.org/10.21947/1775531). CC BY 4.0.</details> |
| 25b | [NREL SUMR-D / CART2](https://data.openei.org/submissions/4189) 🆕 ⚠️ | – | 🇺🇸 on | ✅ | 1 | ? | ❌ | ❌ | 5m | ? | open | [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/) | [📚7](#pubs-25b) | <details><summary>notes</summary>⚠️ Research turbine with highly flexible rotor (ARPA-E SUMR-D project). Power, loads & met during startup/operation/shutdown/parked/idle. .mat & .xlsx with MATLAB loader scripts. CC BY 4.0.</details> |
| 98 | [Engie La Haute Borne](https://opendata-renewables.engie.com/) ⚠️ | – | 🇫🇷 on | ❌ | 4 | 34[^engie] | ❌ | ❌ | 10m | 8y | mirror | [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/) | [📚7](#pubs-98) | <details><summary>notes</summary>Original portal offline. Re-hosted [mirror](https://data.mendeley.com/datasets/vmyg4yp3s8/1): 4 × Senvion MM82, 2013-01-01 - 2020-12-31, 1,057,868 records, CC BY 4.0. Its title misspells the farm as "La Houte Bourne" and locates it in Villeneuve-d'Ascq - the farm is at Vaudeville-le-Haut, Meuse. Check licensing of the 3rd-party re-upload. [Farm info](https://www.thewindpower.net/windfarm_en_3354_la-haute-borne-vaudeville-le-haut.php).</details> |
| 99 | [Levenmouth Turbine](https://pod.ore.catapult.org.uk/data-collection/ldt-turbine-scada-10m) 👎 | – | 🇬🇧 near | ✅ | 1 | >500 | ✅ | ❌ | 10m/1s | 3y | paid | – | [📚10](#pubs-99) | <details><summary>notes</summary>Not available for free (~2000 £).</details> |

[^edp]: Manual annotations of major failures or component replacements.
[^winji]: SCADA error log indicator.
[^hires]: Higher resolution on request.
[^buoy]: Statistics from wave buoy and ground-based LiDAR data.
[^lidar]: Ground-based LiDAR.
[^dundalk]: Gearbox replacement in 2018-2019.
[^bearing]: Single annotated gearbox bearing failure on 2012-11-09 13:00 (sample 1232).
[^engie]: 34 process parameters, each with avg/std/max/min per interval (~136 columns).

## Notebooks - Data Loaders and Overview Plots:
The jupyter notebooks in the 'notebooks' folder contain a data loader for SCADA signals, logs, annotations as well as community annotations (see next sections). The Loader column in the table above indicates whether the respective dataset has already been added. Furthermore, they produce an overview over each dataset such as shown in the following image:

![image](./images/data_overview_example.png)

Also, for each turbine, there is an 'Overview Cockpit' with a power curve plot, a wind rose and the data availability over time. An example is shown here:

![image](./images/turbine_cockpit_example.png)

Lastly, operator annotations are listed, if they are part of the dataset. See e.g. for T01 of the edp data set:

![image](./images/operator_annotations_example.png)

To run the notebooks yourself, please add the respective .csv-files to the data folder.

## Community Annotations:
We want to enable researchers to build upon the findings of others who were previously working with the dataset. For every dataset, we have set up a [community-annotation folder](./communiy_annotations), containing simple CSV's to collect data quality or malfunction related observations. They contain the following columns:

- annot_id: unique annotation identifier (running ascending number) 
- turbine_id: which turbine of the respective dataset is affected?
- signal: which signal exhibits the respective observation?
- time_start / time_stop: during which time is the observation present?
- related_log_message (optional): is there a SCADA log message that coincides with the observation?
- remarks: describe your observation in a few words.

The respective notebooks automatically load, read and display the respective malfunctions. See e.g. this example from T01 of the edp-dataset:

![image](./images/community_annotations_example.png)

## How to contribute:
We welcome contributions to expand the collection of open datasets in this repository as well as community annotations for the datasets. Feel free to create respective PRs :).

## Reviews on Open Wind SCADA Data Sets:
Review and survey papers that collect, categorize or discuss openly available wind turbine SCADA datasets. Many of the datasets in Table 1 are described and analysed in [[3]](#ref3).

- <a id="ref1"></a>[1] Menezes et al. (2020). Wind Farm and Resource Datasets: A Comprehensive Survey and Overview. *Energies*. [doi:10.3390/en13184702](https://doi.org/10.3390/en13184702)
- <a id="ref2"></a>[2] Chatterjee & Dethlefs (2021). Scientometric review of artificial intelligence for operations & maintenance of wind turbines: The past, present and future. *Renewable and Sustainable Energy Reviews*. [doi:10.1016/j.rser.2021.111051](https://doi.org/10.1016/j.rser.2021.111051)
- <a id="ref3"></a>[3] Effenberger & Ludwig (2022). A collection and categorization of open‐source wind and wind power datasets. *Wind Energy*. [doi:10.1002/we.2766](https://doi.org/10.1002/we.2766)
- <a id="ref4"></a>[4] Pandit et al. (2023). SCADA data for wind turbine data-driven condition/performance monitoring: A review on state-of-art, challenges and future trends. *Wind Engineering*. [doi:10.1177/0309524X221124031](https://doi.org/10.1177/0309524X221124031)
- <a id="ref5"></a>[5] Akhtar et al. (2026). Datasets for wind energy forecasting applications: A comprehensive review and benchmarking perspective. *Renewable and Sustainable Energy Reviews*. [doi:10.1016/j.rser.2026.116941](https://doi.org/10.1016/j.rser.2026.116941)
- <a id="ref6"></a>[6] Jia et al. (2026). AI-Driven Fault Detection and O&M for Wind Turbine Drivetrains: A Review of SCADA, CMS and Digital Twin Integration. *Energies*. [doi:10.3390/en19051370](https://doi.org/10.3390/en19051370)

## Publications Using the Datasets:
Scientific publications using the datasets of Table 1, grouped by dataset and numbered consecutively after the [Reviews](#reviews-on-open-wind-scada-data-sets). ⭐ marks the publication introducing the dataset. Publications using several datasets keep their number and link to their first entry. Collected via citation and full-text searches (OpenAlex, DataCite, publisher pages); not exhaustive - additions welcome via PR.

### <a id="pubs-1"></a>1 - EDP Open Data (15)
- <a id="ref7"></a>[7] Roelofs et al. (2021). Autoencoder-based anomaly root cause analysis for wind turbines. *Energy and AI*. [doi:10.1016/j.egyai.2021.100065](https://doi.org/10.1016/j.egyai.2021.100065)
- <a id="ref8"></a>[8] Barber et al. (2022). Enabling Co-Innovation for a Successful Digital Transformation in Wind Energy Using a New Digital Ecosystem and a Fault Detection Case Study. *Energies*. [doi:10.3390/en15155638](https://doi.org/10.3390/en15155638)
- <a id="ref9"></a>[9] Garan et al. (2022). A Data-Centric Machine Learning Methodology: Application on Predictive Maintenance of Wind Turbines. *Energies*. [doi:10.3390/en15030826](https://doi.org/10.3390/en15030826)
- <a id="ref10"></a>[10] Latiffianti et al. (2022). Wind Turbine Gearbox Failure Detection Through Cumulative Sum of Multivariate Time Series Data. *Frontiers in Energy Research*. [doi:10.3389/fenrg.2022.904622](https://doi.org/10.3389/fenrg.2022.904622)
- <a id="ref11"></a>[11] Miele et al. (2022). Deep anomaly detection in horizontal axis wind turbines using Graph Convolutional Autoencoders for Multivariate Time series. *Energy and AI*. [doi:10.1016/j.egyai.2022.100145](https://doi.org/10.1016/j.egyai.2022.100145)
- <a id="ref12"></a>[12] Jankauskas et al. (2023). Exploring the Limits of Early Predictive Maintenance in Wind Turbines Applying an Anomaly Detection Technique. *Sensors*. [doi:10.3390/s23125695](https://doi.org/10.3390/s23125695)
- <a id="ref13"></a>[13] Tang et al. (2023). Fault Diagnosis of Wind Turbine Generators Based on Stacking Integration Algorithm and Adaptive Threshold. *Sensors*. [doi:10.3390/s23136198](https://doi.org/10.3390/s23136198)
- [[67]](#ref67) Gück et al. (2024). CARE to Compare: A Real-World Benchmark Dataset for Early Fault Detection in Wind Turbine Data _(see CARE to Compare)_
- <a id="ref14"></a>[14] Shah et al. (2024). RUL forecasting for wind turbine predictive maintenance based on deep learning. *Heliyon*. [doi:10.1016/j.heliyon.2024.e39268](https://doi.org/10.1016/j.heliyon.2024.e39268)
- <a id="ref15"></a>[15] Barnabei et al. (2025). Semi-Supervised Deep Learning Framework for Predictive Maintenance in Offshore Wind Turbines. *International Journal of Turbomachinery, Propulsion and Power*. [doi:10.3390/ijtpp10030014](https://doi.org/10.3390/ijtpp10030014)
- <a id="ref16"></a>[16] Dao et al. (2025). Analysis of Failures, Downtimes and Reliability of Wind Turbines From SCADA Data. *Wind Energy*. [doi:10.1002/we.70073](https://doi.org/10.1002/we.70073)
- <a id="ref17"></a>[17] Dhungana (2025). A machine learning approach for wind turbine power forecasting for maintenance planning. *Energy Informatics*. [doi:10.1186/s42162-024-00459-4](https://doi.org/10.1186/s42162-024-00459-4)
- <a id="ref18"></a>[18] Nogueira et al. (2025). Wind Turbine Fault Detection Through Autoencoder-Based Neural Network and FMSA. *Sensors*. [doi:10.3390/s25144499](https://doi.org/10.3390/s25144499)
- <a id="ref19"></a>[19] Lu et al. (2026). Towards predictive maintenance: an early warning system for wind turbine generators based on a hybrid deep learning model and dynamic thresholding. *Engineering Research Express*. [doi:10.1088/2631-8695/aeb8e8](https://doi.org/10.1088/2631-8695/aeb8e8)
- <a id="ref20"></a>[20] Nogueira et al. (2026). Anomaly Detection in Wind Turbines: Persistence-Based Alarm Confirmation for False-Alarm Mitigation and Detection-Latency Trade-Offs. *Sensors*. [doi:10.3390/s26123896](https://doi.org/10.3390/s26123896)

### <a id="pubs-2"></a>2 - Winji Gearbox Challenge (2)
- <a id="ref21"></a>[21] ⭐ Barber et al. (2023). Best Practice Data Sharing Guidelines for Wind Turbine Fault Detection Model Evaluation. *Energies*. [doi:10.3390/en16083567](https://doi.org/10.3390/en16083567)
- <a id="ref22"></a>[22] Barber et al. (2023). Can data sharing really provide added value? Practical data sharing recommendations for the wind energy sector. *Journal of Physics: Conference Series*. [doi:10.1088/1742-6596/2507/1/012003](https://doi.org/10.1088/1742-6596/2507/1/012003)

### <a id="pubs-3"></a>3 - Kelmarsh (16)
- <a id="ref23"></a>[23] Im et al. (2023). Comparison and Enhancement of Machine Learning Algorithms for Wind Turbine Output Prediction with Insufficient Data. *Energies*. [doi:10.3390/en16155810](https://doi.org/10.3390/en16155810)
- <a id="ref24"></a>[24] Effenberger et al. (2024). Mind the (spectral) gap: how the temporal resolution of wind data affects multi-decadal wind power forecasts. *Environmental Research Letters*. [doi:10.1088/1748-9326/ad0bd6](https://doi.org/10.1088/1748-9326/ad0bd6)
- <a id="ref25"></a>[25] English & Abolghasemi (2024). Improving the forecast accuracy of wind power by leveraging multiple hierarchical structure. *Sustainable Energy, Grids and Networks*. [doi:10.1016/j.segan.2024.101517](https://doi.org/10.1016/j.segan.2024.101517)
- <a id="ref26"></a>[26] Li et al. (2024). Probability density function based adaptive ensemble learning with global convergence for wind power prediction. *Energy*. [doi:10.1016/j.energy.2024.133573](https://doi.org/10.1016/j.energy.2024.133573)
- <a id="ref27"></a>[27] Tartt et al. (2024). Life extension of wind turbine drivetrains by means of SCADA data: Case study of generator bearings in an onshore wind farm. *Results in Engineering*. [doi:10.1016/j.rineng.2024.102921](https://doi.org/10.1016/j.rineng.2024.102921)
- <a id="ref28"></a>[28] Deignan et al. (2025). Portability of short term wind power forecasting: investigating model calibration using wind power data from Ireland and UK. *Scientific Reports*. [doi:10.1038/s41598-025-08751-3](https://doi.org/10.1038/s41598-025-08751-3)
- <a id="ref29"></a>[29] Fiocchi et al. (2025). Probabilistic Multilayer Perceptrons for Wind Farm Condition Monitoring. *Wind Energy*. [doi:10.1002/we.70012](https://doi.org/10.1002/we.70012)
- <a id="ref30"></a>[30] Grataloup et al. (2025). Wind Turbine Condition Monitoring Based on Intra- and Inter-Farm Federated Learning. *IEEE Access*. [doi:10.1109/ACCESS.2025.3599360](https://doi.org/10.1109/ACCESS.2025.3599360)
- <a id="ref31"></a>[31] Hammer & Barber (2025). Data imputation for SCADA data using Graph Neural Networks. *Journal of Physics: Conference Series*. [doi:10.1088/1742-6596/3025/1/012014](https://doi.org/10.1088/1742-6596/3025/1/012014)
- <a id="ref32"></a>[32] Martín-Calzada et al. (2025). Optimized Sensor Data Preprocessing Using Parameter-Transfer Learning for Wind Turbine Power Curve Modeling. *Sensors*. [doi:10.3390/s25175329](https://doi.org/10.3390/s25175329)
- <a id="ref33"></a>[33] Mazen et al. (2025). A Two‐Stage Model for Outlier Detection and Power Prediction of Wind Turbine Using SCADA Dataset. *International Journal of Energy Research*. [doi:10.1155/er/2527561](https://doi.org/10.1155/er/2527561)
- <a id="ref34"></a>[34] Tartt et al. (2025). On confidence interval-based anomaly detection approach for temperature predictions of wind turbine drivetrains to assist in lifetime extension assessment. *Forschung im Ingenieurwesen*. [doi:10.1007/s10010-025-00791-5](https://doi.org/10.1007/s10010-025-00791-5)
- <a id="ref35"></a>[35] Xu et al. (2025). A cross-dataset benchmark for neural network-based wind power forecasting. *Renewable Energy*. [doi:10.1016/j.renene.2025.123463](https://doi.org/10.1016/j.renene.2025.123463)
- <a id="ref36"></a>[36] Ladopoulou et al. (2026). Probabilistic wind power modelling via heteroscedastic non-stationary gaussian processes. *Energy Reports*. [doi:10.1016/j.egyr.2025.12.032](https://doi.org/10.1016/j.egyr.2025.12.032)
- <a id="ref37"></a>[37] Pandit et al. (2026). SCADA-based early detection of wind turbine yaw motor current failures using Gaussian process surrogate models and Fisher's combined probabilistic alarm thresholding. *Wind Energy and Engineering Research*. [doi:10.1016/j.weer.2026.100031](https://doi.org/10.1016/j.weer.2026.100031)
- <a id="ref38"></a>[38] Park et al. (2026). Structural defects in the Kelmarsh open SCADA dataset: a provenance audit with file reconstruction and downstream consequences. *Wind Energy Science Discussions*. [doi:10.5194/wes-2026-166](https://doi.org/10.5194/wes-2026-166)

### <a id="pubs-4"></a>4 - Penmanshiel (21)
- <a id="ref39"></a>[39] Jenkel et al. (2023). Privacy-Preserving Fleet-Wide Learning of Wind Turbine Conditions with Federated Learning. *Energies*. [doi:10.3390/en16176377](https://doi.org/10.3390/en16176377)
- <a id="ref40"></a>[40] Kousounadis-Knousen et al. (2023). A New Co-Optimized Hybrid Model Based on Multi-Objective Optimization for Probabilistic Wind Power Forecasting in a Spatio–Temporal Framework. *IEEE Access*. [doi:10.1109/ACCESS.2023.3302701](https://doi.org/10.1109/ACCESS.2023.3302701)
- <a id="ref41"></a>[41] Liu et al. (2023). An online transfer learning model for wind turbine power prediction based on spatial feature construction and system-wide update. *Applied Energy*. [doi:10.1016/j.apenergy.2023.121049](https://doi.org/10.1016/j.apenergy.2023.121049)
- <a id="ref42"></a>[42] Wang et al. (2023). A Directional Monitoring Approach of Sequential Incomplete Wind Power Curves with Copula-based Variational Inference. *arXiv*. [doi:10.48550/arXiv.2311.02411](https://doi.org/10.48550/arXiv.2311.02411)
- <a id="ref43"></a>[43] Cai & Li (2024). Short-term wind speed forecast based on dynamic spatio-temporal directed graph attention network. *Applied Energy*. [doi:10.1016/j.apenergy.2024.124124](https://doi.org/10.1016/j.apenergy.2024.124124)
- <a id="ref44"></a>[44] Capelletti et al. (2024). Wind power curve modeling: A probabilistic Beta regression approach. *Renewable Energy*. [doi:10.1016/j.renene.2024.119970](https://doi.org/10.1016/j.renene.2024.119970)
- [[24]](#ref24) Effenberger et al. (2024). Mind the (spectral) gap: how the temporal resolution of wind data affects multi-decadal wind power forecasts _(see Kelmarsh)_
- [[25]](#ref25) English & Abolghasemi (2024). Improving the forecast accuracy of wind power by leveraging multiple hierarchical structure _(see Kelmarsh)_
- [[26]](#ref26) Li et al. (2024). Probability density function based adaptive ensemble learning with global convergence for wind power prediction _(see Kelmarsh)_
- <a id="ref45"></a>[45] Li et al. (2024). Collaborative monitoring of wind turbine performance based on probabilistic power curve comparison. *Renewable Energy*. [doi:10.1016/j.renene.2024.120919](https://doi.org/10.1016/j.renene.2024.120919)
- <a id="ref46"></a>[46] Liu & Hui (2024). Advancing predictive maintenance: a deep learning approach to sensor and event-log data fusion. *Sensor Review*. [doi:10.1108/SR-03-2024-0183](https://doi.org/10.1108/SR-03-2024-0183)
- <a id="ref47"></a>[47] Bronskiy et al. (2025). Enhancing wind turbine fault prediction through integrated SCADA data analysis and machine learning techniques. *IET Conference Proceedings*. [doi:10.1049/icp.2025.0478](https://doi.org/10.1049/icp.2025.0478)
- <a id="ref48"></a>[48] Chen et al. (2025). Wind power generation forecasting system based on multi-model intelligent fusion strategy and probabilistic forecasting technology. *Neural Networks*. [doi:10.1016/j.neunet.2025.107884](https://doi.org/10.1016/j.neunet.2025.107884)
- [[28]](#ref28) Deignan et al. (2025). Portability of short term wind power forecasting: investigating model calibration using wind power data from Ireland and UK _(see Kelmarsh)_
- <a id="ref49"></a>[49] Erturk et al. (2025). A Digital Twin model for predicting wind turbine performance using federated learning. *Energy*. [doi:10.1016/j.energy.2025.138644](https://doi.org/10.1016/j.energy.2025.138644)
- [[30]](#ref30) Grataloup et al. (2025). Wind Turbine Condition Monitoring Based on Intra- and Inter-Farm Federated Learning _(see Kelmarsh)_
- [[31]](#ref31) Hammer & Barber (2025). Data imputation for SCADA data using Graph Neural Networks _(see Kelmarsh)_
- [[35]](#ref35) Xu et al. (2025). A cross-dataset benchmark for neural network-based wind power forecasting _(see Kelmarsh)_
- <a id="ref50"></a>[50] Hu & Hu (2026). A Physics-Guided Graph Transformer for Short-Term SCADA-Based Multi-Turbine Wind Power Forecasting. *Sensors*. [doi:10.3390/s26216672](https://doi.org/10.3390/s26216672)
- <a id="ref51"></a>[51] Neshat et al. (2026). Physics-informed LLM-guided dynamic spatio-temporal graph deep network for short-term wind farm power forecasting. *Energy Conversion and Management*. [doi:10.1016/j.enconman.2026.121974](https://doi.org/10.1016/j.enconman.2026.121974)
- <a id="ref52"></a>[52] Windmann et al. (2026). Benchmarking Sensor-Fault Robustness in Forecasting. *arXiv*. [doi:10.48550/arXiv.2605.10822](https://doi.org/10.48550/arXiv.2605.10822)

### <a id="pubs-5"></a>5 - Ørsted Anholt Offshore (10)
_Early DTU works obtained the data via a direct DTU–Ørsted collaboration rather than the data-sharing programme._

- <a id="ref53"></a>[53] Ahsbahs et al. (2018). Applications of satellite winds for the offshore wind farm site Anholt. *Wind Energy Science*. [doi:10.5194/wes-3-573-2018](https://doi.org/10.5194/wes-3-573-2018)
- <a id="ref54"></a>[54] Peña et al. (2018). On wake modeling, wind-farm gradients, and AEP predictions at the Anholt wind farm. *Wind Energy Science*. [doi:10.5194/wes-3-191-2018](https://doi.org/10.5194/wes-3-191-2018)
- <a id="ref55"></a>[55] Sanz Rodrigo et al. (2020). Validation of Meso-Wake Models for Array Efficiency Prediction Using Operational Data from Five Offshore Wind Farms. *Journal of Physics: Conference Series*. [doi:10.1088/1742-6596/1618/6/062044](https://doi.org/10.1088/1742-6596/1618/6/062044)
- <a id="ref56"></a>[56] Doekemeijer et al. (2022). Comparison of the Gaussian Wind Farm Model with Historical Data of Three Offshore Wind Farms. *Energies*. [doi:10.3390/en15061964](https://doi.org/10.3390/en15061964)
- <a id="ref57"></a>[57] Ryu et al. (2022). Analysis of Vertical Wind Shear Effects on Offshore Wind Energy Prediction Accuracy Applying Rotor Equivalent Wind Speed and the Relationship with Atmospheric Stability. *Applied Sciences*. [doi:10.3390/app12146949](https://doi.org/10.3390/app12146949)
- <a id="ref58"></a>[58] Chanprasert et al. (2024). Wake Effect Quantification using SCADA Data and LES Modelling of an Operational Offshore Wind Farm. *Journal of Physics: Conference Series*. [doi:10.1088/1742-6596/2767/9/092012](https://doi.org/10.1088/1742-6596/2767/9/092012)
- <a id="ref59"></a>[59] Kim et al. (2024). Accuracy of a short-term wind power forecasting model based on deep learning using LiDAR-SCADA integration: A case study of the 400-MW Anholt offshore wind farm.. *Applied Energy*. [doi:10.1016/j.apenergy.2024.123882](https://doi.org/10.1016/j.apenergy.2024.123882)
- <a id="ref60"></a>[60] Mian et al. (2025). Extracting Data-Driven Insights from LiDAR and SCADA Data for Improved Analysis of Offshore Wind Farms. *Journal of Physics: Conference Series*. [doi:10.1088/1742-6596/3131/1/012031](https://doi.org/10.1088/1742-6596/3131/1/012031)
- <a id="ref61"></a>[61] Lejeune et al. (2026). Correlating wake-model performance to the atmospheric state: a SCADA-based analysis at two offshore wind farms. *Wind Energy Science Discussions*. [doi:10.5194/wes-2026-164](https://doi.org/10.5194/wes-2026-164)
- <a id="ref62"></a>[62] Nordbak et al. (2026). Short-Term Offshore Wind Power Forecasting with TimeGPT: Insights from SCADA and LiDAR Measurements. *Journal of Physics: Conference Series*. [doi:10.1088/1742-6596/3224/3/032121](https://doi.org/10.1088/1742-6596/3224/3/032121)

### <a id="pubs-6"></a>6 - Ørsted Westermost Rough (7)
- [[56]](#ref56) Doekemeijer et al. (2022). Comparison of the Gaussian Wind Farm Model with Historical Data of Three Offshore Wind Farms _(see Ørsted Anholt Offshore)_
- <a id="ref63"></a>[63] Lanzilao & Meyers (2022). A new wake‐merging method for wind‐farm power prediction in the presence of heterogeneous background velocity fields. *Wind Energy*. [doi:10.1002/we.2669](https://doi.org/10.1002/we.2669)
- <a id="ref64"></a>[64] Aerts et al. (2023). Bayesian uncertainty quantification framework for wake model calibration and validation with historical wind farm power data. *Wind Energy*. [doi:10.1002/we.2841](https://doi.org/10.1002/we.2841)
- <a id="ref65"></a>[65] Sanchez Gomez et al. (2024). Can mesoscale models capture the effect from cluster wakes offshore?. *Journal of Physics: Conference Series*. [doi:10.1088/1742-6596/2767/6/062013](https://doi.org/10.1088/1742-6596/2767/6/062013)
- [[60]](#ref60) Mian et al. (2025). Extracting Data-Driven Insights from LiDAR and SCADA Data for Improved Analysis of Offshore Wind Farms _(see Ørsted Anholt Offshore)_
- <a id="ref66"></a>[66] Lejeune et al. (2026). Toward an integrated wake model calibration tool fed with SCADA data: correlating wake model performances to the atmospheric state. *Journal of Physics: Conference Series*. [doi:10.1088/1742-6596/3224/3/032008](https://doi.org/10.1088/1742-6596/3224/3/032008)
- [[61]](#ref61) Lejeune et al. (2026). Correlating wake-model performance to the atmospheric state: a SCADA-based analysis at two offshore wind farms _(see Ørsted Anholt Offshore)_

### <a id="pubs-7a-7b"></a>7a/7b - CARE to Compare (13)
- <a id="ref67"></a>[67] ⭐ Gück et al. (2024). CARE to Compare: A Real-World Benchmark Dataset for Early Fault Detection in Wind Turbine Data. *Data*. [doi:10.3390/data9120138](https://doi.org/10.3390/data9120138)
- <a id="ref68"></a>[68] Ciocan et al. (2025). Energy-Aware Anomaly Detection in Wind Turbine SCADA Systems. *2025 International Conference on Software, Telecommunications and Computer Networks (SoftCOM)*. [doi:10.23919/softcom66362.2025.11197377](https://doi.org/10.23919/softcom66362.2025.11197377)
- <a id="ref69"></a>[69] Hassan et al. (2025). AI-Enabled Predictive Maintenance for Offshore Wind Turbines: An Empirical Study. *2025 International Conference on Future Energy Solutions (FES)*. [doi:10.1109/FES65767.2025.11341781](https://doi.org/10.1109/FES65767.2025.11341781)
- <a id="ref70"></a>[70] Nair et al. (2025). Hybrid Autoencoder-Based Framework for Early Fault Detection in Wind Turbines. *arXiv*. [doi:10.48550/arXiv.2510.15010](https://doi.org/10.48550/arXiv.2510.15010)
- <a id="ref71"></a>[71] Sudhakara et al. (2025). Native AI-based Predictive Operational Resiliency in Cyber-Physical Energy Systems. *2025 International Wireless Communications and Mobile Computing (IWCMC)*. [doi:10.1109/IWCMC65282.2025.11059490](https://doi.org/10.1109/IWCMC65282.2025.11059490)
- <a id="ref72"></a>[72] Ata et al. (2026). Early prediction of wind turbine anomalies using 1D-CNN and temporal feature engineering on multi-source SCADA data. *Scientific Reports*. [doi:10.1038/s41598-026-41571-7](https://doi.org/10.1038/s41598-026-41571-7)
- <a id="ref73"></a>[73] Ata et al. (2026). Explainable attention-augmented hybrid CNN–LSTM framework for early and accurate wind turbine anomaly detection. *The Journal of Supercomputing*. [doi:10.1007/s11227-026-08593-4](https://doi.org/10.1007/s11227-026-08593-4)
- <a id="ref74"></a>[74] Haneef et al. (2026). Uncertainty-Calibrated Residual Conformal Monitoring of Wind Turbine SCADA Data for Cross-Asset Anomaly Detection Under Distribution Shift. *Information*. [doi:10.3390/info17090930](https://doi.org/10.3390/info17090930)
- <a id="ref75"></a>[75] Liu et al. (2026). Chronologically calibrated PCA for wind-turbine SCADA health monitoring: a leakage-controlled CARE v6 benchmark. *Wind Energy Science Discussions*. [doi:10.5194/wes-2026-145](https://doi.org/10.5194/wes-2026-145)
- <a id="ref76"></a>[76] Nyamato et al. (2026). Physics-Informed Validation of an XGBoost Decision Layer for SCADA-Based Wind Turbine Anomaly Detection. *Energies*. [doi:10.3390/en19133142](https://doi.org/10.3390/en19133142)
- <a id="ref77"></a>[77] Osterbrink et al. (2026). AI-enhanced diagnostics for manufacturer-independent validation of wind turbine performance: Results from the WindKI project. *Journal of Physics: Conference Series*. [doi:10.1088/1742-6596/3224/6/062040](https://doi.org/10.1088/1742-6596/3224/6/062040)
- <a id="ref78"></a>[78] O’Connor et al. (2026). Detecting Changes in Normal Wind Turbine Operations Using Data Driven Approaches. *Journal of Physics: Conference Series*. [doi:10.1088/1742-6596/3224/6/062018](https://doi.org/10.1088/1742-6596/3224/6/062018)
- <a id="ref79"></a>[79] Yin & Gao (2026). SWIFT: Spectral Wavelet Integrated Fault Transformer for Wind Turbine Anomaly Detection. *IEEE Access*. [doi:10.1109/ACCESS.2026.3715102](https://doi.org/10.1109/ACCESS.2026.3715102)

### <a id="pubs-8"></a>8 - Fuhrländer Farm (4)
- <a id="ref80"></a>[80] ⭐ Marti-Puig et al. (2024). Wind turbine database for intelligent operation and maintenance strategies. *Scientific Data*. [doi:10.1038/s41597-024-03067-9](https://doi.org/10.1038/s41597-024-03067-9)
- <a id="ref81"></a>[81] Marti-Puig et al. (2019). Feature Selection Algorithms for Wind Turbine Failure Prediction. *Energies*. [doi:10.3390/en12030453](https://doi.org/10.3390/en12030453)
- <a id="ref82"></a>[82] Marti-Puig & Núñez-Vilaplana (2024). Dynamic Clustering of Wind Turbines Using SCADA Signal Analysis. *Energies*. [doi:10.3390/en17112514](https://doi.org/10.3390/en17112514)
- <a id="ref83"></a>[83] Gutierrez et al. (2026). Temporal Attribution Matrix for Tracking XAI Feature Importance Evolution in Wind Turbine Gearbox Degradation Detection Using SCADA Data. *Energies*. [doi:10.3390/en19133072](https://doi.org/10.3390/en19133072)

### <a id="pubs-9a-9d"></a>9a-9d - DSforWind (7)
- <a id="ref84"></a>[84] ⭐ Lee et al. (2015). Power Curve Estimation With Multivariate Environmental Factors for Inland and Offshore Wind Farms. *Journal of the American Statistical Association*. [doi:10.1080/01621459.2014.977385](https://doi.org/10.1080/01621459.2014.977385)
- <a id="ref85"></a>[85] Pang et al. (2021). Correlation analysis of factors affecting wind power based on machine learning and Shapley value. *IET Energy Systems Integration*. [doi:10.1049/esi2.12022](https://doi.org/10.1049/esi2.12022)
- <a id="ref86"></a>[86] Chen & Zhang (2022). Density Regression with Conditional Support Points. *Technometrics*. [doi:10.1080/00401706.2022.2044384](https://doi.org/10.1080/00401706.2022.2044384)
- <a id="ref87"></a>[87] Ding et al. (2022). Data-Driven wind turbine performance assessment and quantification using SCADA data and field measurements. *Frontiers in Energy Research*. [doi:10.3389/fenrg.2022.1050342](https://doi.org/10.3389/fenrg.2022.1050342)
- <a id="ref88"></a>[88] Prakash et al. (2023). The Temporal Overfitting Problem with Applications in Wind Power Curve Modeling. *Technometrics*. [doi:10.1080/00401706.2022.2069158](https://doi.org/10.1080/00401706.2022.2069158)
- <a id="ref89"></a>[89] Wang et al. (2023). Wind Power Curve Modeling With Large-Scale Generalized Kernel-Based Regression Model. *IEEE Transactions on Sustainable Energy*. [doi:10.1109/TSTE.2023.3276906](https://doi.org/10.1109/TSTE.2023.3276906)
- <a id="ref90"></a>[90] Aydemir & Öztürk (2026). Power curve estimation and feature importance quantification for offshore wind turbines based on XGBoost regression. *International Journal of Green Energy*. [doi:10.1080/15435075.2026.2628952](https://doi.org/10.1080/15435075.2026.2628952)

### <a id="pubs-10"></a>10 - PCWG Data Sets (1)
_Based on the confidential PCWG Share-3 exercise; no independent use of the public datasets found._

- <a id="ref91"></a>[91] Lee et al. (2020). The Power Curve Working Group's assessment of wind turbine power performance prediction methods. *Wind Energy Science*. [doi:10.5194/wes-5-199-2020](https://doi.org/10.5194/wes-5-199-2020)

### <a id="pubs-11a"></a>11a - Norrekaer Windfarm (2)
- <a id="ref92"></a>[92] Piao et al. (2026). Fourier Geometric Wind Power Forecasting with Numerical Weather Prediction. *Proceedings of the 32nd ACM SIGKDD Conference on Knowledge Discovery and Data Mining V.2*. [doi:10.1145/3770855.3818905](https://doi.org/10.1145/3770855.3818905)
- <a id="ref93"></a>[93] Saeed (2026). WakePGA: Dynamic Physics-Guided Attention for Wind Farm SCADA Reconstruction Under Changing Wind Directions. *SSRN preprint*. [doi:10.2139/ssrn.7021432](https://doi.org/10.2139/ssrn.7021432)

### <a id="pubs-11b"></a>11b - Delabole Windfarm (0)
_No publications found._


### <a id="pubs-12"></a>12 - Dundalk IoT (11)
- <a id="ref94"></a>[94] ⭐ Byrne & MacArtain (2023). Multi-annual time series operational data for a Vestas V52 wind turbine located in a coastal peri-urban environment in Ireland. *Data in Brief*. [doi:10.1016/j.dib.2023.109227](https://doi.org/10.1016/j.dib.2023.109227)
- <a id="ref95"></a>[95] Astolfi et al. (2020). Analysis of Wind Turbine Aging through Operation Curves. *Energies*. [doi:10.3390/en13215623](https://doi.org/10.3390/en13215623)
- <a id="ref96"></a>[96] Byrne et al. (2020). A Study of Wind Turbine Performance Decline with Age through Operation Data Analysis. *Energies*. [doi:10.3390/en13082086](https://doi.org/10.3390/en13082086)
- <a id="ref97"></a>[97] Astolfi et al. (2021). Estimation of the Performance Aging of the Vestas V52 Wind Turbine through Comparative Test Case Analysis. *Energies*. [doi:10.3390/en14040915](https://doi.org/10.3390/en14040915)
- <a id="ref98"></a>[98] Byrne & MacArtain (2022). The 15-year operational experiences of an 850 kW peri-urban wind turbine: Lessons learned from a behind-the-meter installation in Ireland. *Energy for Sustainable Development*. [doi:10.1016/j.esd.2022.08.011](https://doi.org/10.1016/j.esd.2022.08.011)
- <a id="ref99"></a>[99] Zakynthinos et al. (2025). A Meta-Learning Framework for Short-Term Wind Power Forecasting with SCADA and Weather Data. *2025 16th International Conference on Information, Intelligence, Systems &amp; Applications (IISA)*. [doi:10.1109/iisa66859.2025.11311208](https://doi.org/10.1109/iisa66859.2025.11311208)
- <a id="ref100"></a>[100] Ahsan & Dao (2026). Multi-Channel SCADA-Based Image-Driven Power Prediction for Wind Turbines Using Optimized LeNet-5-LSTM Hybrid Neural Architecture. *Energies*. [doi:10.3390/en19051169](https://doi.org/10.3390/en19051169)
- <a id="ref101"></a>[101] Ez-Zahiri et al. (2026). Automated Labeling Procedure for Wind Turbine SCADA Data with Iterative Refinement and Model-Based Validation. *Electronics*. [doi:10.3390/electronics15132907](https://doi.org/10.3390/electronics15132907)
- <a id="ref102"></a>[102] Mia et al. (2026). A novel CNN–attention–BiLSTM hybrid deep learning model for wind turbine power forecasting using SCADA data. *Energy Conversion and Management: X*. [doi:10.1016/j.ecmx.2026.102367](https://doi.org/10.1016/j.ecmx.2026.102367)
- <a id="ref103"></a>[103] Sakib et al. (2026). C-MixNet: Regime-aware clustering and MDN-augmented LUBE for uncertainty-aware wind power forecasting. *Energy Reports*. [doi:10.1016/j.egyr.2026.109806](https://doi.org/10.1016/j.egyr.2026.109806)
- <a id="ref104"></a>[104] Sifakis et al. (2026). Operational Digital Shadow for Onshore Wind Energy Systems. *Energies*. [doi:10.3390/en19122897](https://doi.org/10.3390/en19122897)

### <a id="pubs-13"></a>13 - Kaggle Wind Turbine (8)
_Very widely used (~80+ papers); representative selection._

- <a id="ref105"></a>[105] Delgado & Fahim (2020). Wind Turbine Data Analysis and LSTM-Based Prediction in SCADA System. *Energies*. [doi:10.3390/en14010125](https://doi.org/10.3390/en14010125)
- <a id="ref106"></a>[106] Lin et al. (2021). Wind Power Forecasting with Deep Learning Networks: Time-Series Forecasting. *Applied Sciences*. [doi:10.3390/app112110335](https://doi.org/10.3390/app112110335)
- <a id="ref107"></a>[107] Singh et al. (2021). A Machine Learning-Based Gradient Boosting Regression Approach for Wind Power Production Forecasting: A Step towards Smart Grid Environments. *Energies*. [doi:10.3390/en14165196](https://doi.org/10.3390/en14165196)
- <a id="ref108"></a>[108] Fahim et al. (2022). Machine Learning-Based Digital Twin for Predictive Modeling in Wind Turbines. *IEEE Access*. [doi:10.1109/access.2022.3147602](https://doi.org/10.1109/access.2022.3147602)
- <a id="ref109"></a>[109] Singh & Rizwan (2022). SCADA system dataset exploration and machine learning based forecast for wind turbines. *Results in Engineering*. [doi:10.1016/j.rineng.2022.100640](https://doi.org/10.1016/j.rineng.2022.100640)
- <a id="ref110"></a>[110] Mushtaq et al. (2023). Multivariate wind power curve modeling using multivariate adaptive regression splines and regression trees. *PLOS ONE*. [doi:10.1371/journal.pone.0290316](https://doi.org/10.1371/journal.pone.0290316)
- <a id="ref111"></a>[111] Tarek et al. (2023). Wind Power Prediction Based on Machine Learning and Deep Learning Models. *Computers, Materials & Continua*. [doi:10.32604/cmc.2023.032533](https://doi.org/10.32604/cmc.2023.032533)
- <a id="ref112"></a>[112] Oyucu & Aksöz (2024). Integrating Machine Learning and MLOps for Wind Energy Forecasting: A Comparative Analysis and Optimization Study on Türkiye’s Wind Data. *Applied Sciences*. [doi:10.3390/app14093725](https://doi.org/10.3390/app14093725)

### <a id="pubs-14"></a>14 - Small São Paulo (3)
- <a id="ref113"></a>[113] ⭐ Bassi et al. (2023). Dataset on SCADA Data of an Urban Small Wind Turbine Operation in São Paulo, Brazil. *Data*. [doi:10.3390/data8030052](https://doi.org/10.3390/data8030052)
- <a id="ref114"></a>[114] Bassi et al. (2022). Implantation, Operation Data and Performance Assessment of An Urban Area Grid-Connected Small Wind Turbine. *Wind*. [doi:10.3390/wind2040037](https://doi.org/10.3390/wind2040037)
- <a id="ref115"></a>[115] Pawlik (2026). Evaluating Reconstruction-Based and Proximity-Based Methods: A Four-Way Comparison (AE, LSTM-AE, OCSVM, IF) in SCADA Anomaly Detection Under Inverted Imbalance. *Future Internet*. [doi:10.3390/fi18020096](https://doi.org/10.3390/fi18020096)

### <a id="pubs-15"></a>15 - Björkö Wind Turbine (1)
- <a id="ref116"></a>[116] Panda et al. (2026). Rotor effective wind field estimation and multi-body dynamic characterization of a 45 kW horizontal axis wind turbine. *Renewable Energy*. [doi:10.1016/j.renene.2025.124343](https://doi.org/10.1016/j.renene.2025.124343)

### <a id="pubs-16"></a>16 - IET-OST Turbine (4)
_The last three use the earlier ETH Zürich release of the same turbine ([Zenodo 4964458](https://doi.org/10.5281/zenodo.4964458))._

- <a id="ref117"></a>[117] Hermes et al. (2025). Uncertainty propagation and subspace identification of isotropic wind turbines with the PO-MOESP algorithm. *Mechanical Systems and Signal Processing*. [doi:10.1016/j.ymssp.2025.113159](https://doi.org/10.1016/j.ymssp.2025.113159)
- <a id="ref118"></a>[118] Wang et al. (2025). Fault detection in wind turbines using health index monitoring with variational autoencoders. *Wind Energy Science*. [doi:10.5194/wes-10-2841-2025](https://doi.org/10.5194/wes-10-2841-2025)
- <a id="ref119"></a>[119] Alqahtani et al. (2026). Enhancing SCADA Security in Critical Infrastructure: A Multi-Layered Architecture Using IoT-Based Monitoring and AI-Driven Anomaly Detection. *International Journal of Advanced Computer Science and Applications*. [doi:10.14569/ijacsa.2026.0170187](https://doi.org/10.14569/ijacsa.2026.0170187)
- <a id="ref120"></a>[120] Velandia-Cárdenas et al. (2026). Enhancing Wind Turbine Diagnostics With SCADA‐Vibration Fusion, Contrastive Learning, and Linear Predictive Coefficients. *Structural Control and Health Monitoring*. [doi:10.1155/stc/4023580](https://doi.org/10.1155/stc/4023580)

### <a id="pubs-17-18"></a>17/18 - Pedra do Sal & Beberibe (5)
- <a id="ref121"></a>[121] ⭐ Sakagami et al. (2015). Wind Shear Assessment Using Wind LiDAR Profiler and Sonic 3D Anemometer for Wind Energy Applications—Preliminary Results. *Renewable Energy in the Service of Mankind Vol I*. [doi:10.1007/978-3-319-17777-9_80](https://doi.org/10.1007/978-3-319-17777-9_80)
- <a id="ref122"></a>[122] Sakagami et al. (2014). Logarithmic Wind Profile: A Stability Wind Shear Term. *arXiv*. [doi:10.48550/arXiv.1405.5158](https://doi.org/10.48550/arXiv.1405.5158)
- <a id="ref123"></a>[123] Barber (2020). Application of a new machine learning method for site-dependent power curve prediction to field measurement data. *Zenodo*. [doi:10.5281/zenodo.4094618](https://doi.org/10.5281/zenodo.4094618)
- <a id="ref124"></a>[124] Sakagami et al. (2023). Power curve performance of coastal turbines subject to low turbulence intensity offshore winds. *Journal of the Brazilian Society of Mechanical Sciences and Engineering*. [doi:10.1007/s40430-022-03942-9](https://doi.org/10.1007/s40430-022-03942-9)
- [[35]](#ref35) Xu et al. (2025). A cross-dataset benchmark for neural network-based wind power forecasting _(see Kelmarsh)_

### <a id="pubs-19"></a>19 - SMARTEOLE Wind Farm (5)
_Göçmen 2022, Duc 2019 and Hegazy 2022 use data from earlier campaigns at the same farm._

- <a id="ref125"></a>[125] ⭐ Simley et al. (2021). Results from a wake-steering experiment at a commercial wind plant: investigating the wind speed dependence of wake-steering performance. *Wind Energy Science*. [doi:10.5194/wes-6-1427-2021](https://doi.org/10.5194/wes-6-1427-2021)
- <a id="ref126"></a>[126] Duc et al. (2019). Local turbulence parameterization improves the Jensen wake model and its implementation for power optimization of an operating wind farm. *Wind Energy Science*. [doi:10.5194/wes-4-287-2019](https://doi.org/10.5194/wes-4-287-2019)
- <a id="ref127"></a>[127] Göçmen et al. (2022). FarmConners wind farm flow control benchmark – Part 1: Blind test results. *Wind Energy Science*. [doi:10.5194/wes-7-1791-2022](https://doi.org/10.5194/wes-7-1791-2022)
- <a id="ref128"></a>[128] Hegazy et al. (2022). LiDAR and SCADA data processing for interacting wind turbine wakes with comparison to analytical wake models. *Renewable Energy*. [doi:10.1016/j.renene.2021.09.019](https://doi.org/10.1016/j.renene.2021.09.019)
- <a id="ref129"></a>[129] Post et al. (2024). Measuring wake deflection from SCADA data during wake steering using machine learning. *Journal of Physics: Conference Series*. [doi:10.1088/1742-6596/2767/4/042031](https://doi.org/10.1088/1742-6596/2767/4/042031)

### <a id="pubs-20"></a>20 - Loegtved VestasV100 (0)
_No publications found (Kaggle notebooks only)._


### <a id="pubs-21"></a>21 - Hill of Towie (5)
- <a id="ref130"></a>[130] Rashidi et al. (2025). A Multi-Phase Deep Learning Framework for Multi-Step Short-Term Wind Power Forecasting in Presence of Uncertainties. *IEEE Access*. [doi:10.1109/access.2025.3631586](https://doi.org/10.1109/access.2025.3631586)
- <a id="ref131"></a>[131] Chopard et al. (2026). Combination of turbine-specific and neighbor-based power prediction for accurate and robust under-performance diagnosis. *Journal of Physics: Conference Series*. [doi:10.1088/1742-6596/3224/6/062065](https://doi.org/10.1088/1742-6596/3224/6/062065)
- <a id="ref132"></a>[132] Si et al. (2026). A dynamic multi-graph spatio-temporal framework for probabilistic wind power and ramp event forecasting. *Sustainable Energy Technologies and Assessments*. [doi:10.1016/j.seta.2026.105477](https://doi.org/10.1016/j.seta.2026.105477)
- <a id="ref133"></a>[133] Wang & Vidal (2026). Neighbor-Based Estimation of Wind Turbine Power for Upgrade Performance Assessment. *Journal of Physics: Conference Series*. [doi:10.1088/1742-6596/3224/6/062024](https://doi.org/10.1088/1742-6596/3224/6/062024)
- <a id="ref134"></a>[134] Wang & Vidal (2026). A Probabilistic Baseline Learning Framework for SCADA-Based Wind Turbine Aging Diagnosis and Multi-Scale Performance Degradation Analysis. *PHM Society European Conference*. [doi:10.36001/phme.2026.v9i1.4851](https://doi.org/10.36001/phme.2026.v9i1.4851)

### <a id="pubs-22"></a>22 - Baltic Coast Siemens 2MW (5)
_All by the dataset's author group (listed as related works on the Mendeley record)._

- <a id="ref135"></a>[135] ⭐ Dao et al. (2024). Anomaly detection of wind turbines based on stationarity analysis of SCADA data. *Renewable Energy*. [doi:10.1016/j.renene.2024.121076](https://doi.org/10.1016/j.renene.2024.121076)
- <a id="ref136"></a>[136] Zolna et al. (2015). Nonlinear Cointegration Approach for Condition Monitoring of Wind Turbines. *Mathematical Problems in Engineering*. [doi:10.1155/2015/978156](https://doi.org/10.1155/2015/978156)
- <a id="ref137"></a>[137] Dao et al. (2018). Condition monitoring and fault detection in wind turbines based on cointegration analysis of SCADA data. *Renewable Energy*. [doi:10.1016/j.renene.2017.06.089](https://doi.org/10.1016/j.renene.2017.06.089)
- <a id="ref138"></a>[138] Dao (2021). A CUSUM-Based Approach for Condition Monitoring and Fault Diagnosis of Wind Turbines. *Energies*. [doi:10.3390/en14113236](https://doi.org/10.3390/en14113236)
- <a id="ref139"></a>[139] Dao (2022). Condition monitoring and fault diagnosis of wind turbines based on structural break detection in SCADA data. *Renewable Energy*. [doi:10.1016/j.renene.2021.12.051](https://doi.org/10.1016/j.renene.2021.12.051)

### <a id="pubs-23"></a>23 - SDWPF (10)
_Very widely used; representative selection._

- <a id="ref140"></a>[140] ⭐ Zhou et al. (2024). SDWPF: A Dataset for Spatial Dynamic Wind Power Forecasting over a Large Turbine Array. *Scientific Data*. [doi:10.1038/s41597-024-03427-5](https://doi.org/10.1038/s41597-024-03427-5)
- <a id="ref141"></a>[141] Zhou et al. (2022). SDWPF: A Dataset for Spatial Dynamic Wind Power Forecasting Challenge at KDD Cup 2022. *arXiv*. [doi:10.48550/arXiv.2208.04360](https://doi.org/10.48550/arXiv.2208.04360)
- <a id="ref142"></a>[142] Jiang et al. (2023). BUAA_BIGSCity: Spatial-Temporal Graph Neural Network for Wind Power Forecasting in Baidu KDD CUP 2022. *arXiv*. [doi:10.48550/arXiv.2302.11159](https://doi.org/10.48550/arXiv.2302.11159)
- <a id="ref143"></a>[143] Zhang et al. (2023). Long-term Wind Power Forecasting with Hierarchical Spatial-Temporal Transformer. *Proceedings of the Thirty-Second International Joint Conference on Artificial Intelligence*. [doi:10.24963/ijcai.2023/700](https://doi.org/10.24963/ijcai.2023/700)
- <a id="ref144"></a>[144] Peng et al. (2024). A graph attention network with spatio-temporal wind propagation graph for wind power ramp events prediction. *Renewable Energy*. [doi:10.1016/j.renene.2024.121280](https://doi.org/10.1016/j.renene.2024.121280)
- <a id="ref145"></a>[145] Qiu et al. (2024). A novel temporal–spatial graph neural network for wind power forecasting considering blockage effects. *Renewable Energy*. [doi:10.1016/j.renene.2024.120499](https://doi.org/10.1016/j.renene.2024.120499)
- <a id="ref146"></a>[146] Woo et al. (2024). Unified Training of Universal Time Series Forecasting Transformers. *arXiv*. [doi:10.48550/arXiv.2402.02592](https://doi.org/10.48550/arXiv.2402.02592)
- <a id="ref147"></a>[147] Zhao et al. (2024). Spatial correlation learning based on graph neural network for medium-term wind power forecasting. *Energy*. [doi:10.1016/j.energy.2024.131164](https://doi.org/10.1016/j.energy.2024.131164)
- <a id="ref148"></a>[148] Hou et al. (2025). Spatiotemporal forecasting using multi-graph neural network assisted dual domain transformer for wind power. *Energy Conversion and Management*. [doi:10.1016/j.enconman.2024.119393](https://doi.org/10.1016/j.enconman.2024.119393)
- [[35]](#ref35) Xu et al. (2025). A cross-dataset benchmark for neural network-based wind power forecasting _(see Kelmarsh)_

### <a id="pubs-24"></a>24 - Sotavento (7)
- <a id="ref149"></a>[149] Safari et al. (2018). Novel Multi-Step Short-Term Wind Power Prediction Framework Based on Chaotic Time Series Analysis and Singular Spectrum Analysis. *IEEE Transactions on Power Systems*. [doi:10.1109/TPWRS.2017.2694705](https://doi.org/10.1109/TPWRS.2017.2694705)
- <a id="ref150"></a>[150] Wang et al. (2018). Deep belief network based k-means cluster approach for short-term wind power forecasting. *Energy*. [doi:10.1016/j.energy.2018.09.118](https://doi.org/10.1016/j.energy.2018.09.118)
- <a id="ref151"></a>[151] Abedinia et al. (2020). Improved EMD-Based Complex Prediction Model for Wind Power Forecasting. *IEEE Transactions on Sustainable Energy*. [doi:10.1109/TSTE.2020.2976038](https://doi.org/10.1109/TSTE.2020.2976038)
- <a id="ref152"></a>[152] Memarzadeh & Keynia (2020). A new short-term wind speed forecasting method based on fine-tuned LSTM neural network and optimal input sets. *Energy Conversion and Management*. [doi:10.1016/j.enconman.2020.112824](https://doi.org/10.1016/j.enconman.2020.112824)
- <a id="ref153"></a>[153] Wang et al. (2021). Effective wind power prediction using novel deep learning network: Stacked independently recurrent autoencoder. *Renewable Energy*. [doi:10.1016/j.renene.2020.09.108](https://doi.org/10.1016/j.renene.2020.09.108)
- <a id="ref154"></a>[154] Zhang et al. (2024). Wind power forecasting system with data enhancement and algorithm improvement. *Renewable and Sustainable Energy Reviews*. [doi:10.1016/j.rser.2024.114349](https://doi.org/10.1016/j.rser.2024.114349)
- <a id="ref155"></a>[155] Jin et al. (2025). Wind power forecasting for newly built wind farms based on deep learning with dual-stage attention mechanism and adaptive transfer learning. *Energy*. [doi:10.1016/j.energy.2025.138275](https://doi.org/10.1016/j.energy.2025.138275)

### <a id="pubs-25a"></a>25a - NREL Flatirons GE 1.5MW SLE (1)
- <a id="ref156"></a>[156] ⭐ Hamilton et al. (2021). Aeroacoustic Assessment of Wind Plant Controls. *NREL Technical Report*. [doi:10.2172/1785330](https://doi.org/10.2172/1785330)

### <a id="pubs-25b"></a>25b - NREL SUMR-D / CART2 (7)
_Mostly by the SUMR project team. Dataset DOI: [10.21947/1888562](https://doi.org/10.21947/1888562)._

- <a id="ref157"></a>[157] Bay et al. (2019). Design and Testing of a Scaled Demonstrator Turbine at the National Wind Technology Center. *AIAA Scitech 2019 Forum*. [doi:10.2514/6.2019-1068](https://doi.org/10.2514/6.2019-1068)
- <a id="ref158"></a>[158] Chetan et al. (2021). Multi‐fidelity digital twin structural model for a sub‐scale downwind wind turbine rotor blade. *Wind Energy*. [doi:10.1002/we.2636](https://doi.org/10.1002/we.2636)
- <a id="ref159"></a>[159] Kaminski et al. (2021). Gravo‐aeroelastic scaling of a 13‐MW downwind rotor for 20% scale blades. *Wind Energy*. [doi:10.1002/we.2569](https://doi.org/10.1002/we.2569)
- <a id="ref160"></a>[160] Loth et al. (2022). Field tests of a highly flexible downwind ultralight rotor to mimic a 13-MW turbine rotor. *Journal of Physics: Conference Series*. [doi:10.1088/1742-6596/2265/3/032031](https://doi.org/10.1088/1742-6596/2265/3/032031)
- <a id="ref161"></a>[161] Phadnis & Pao (2022). On the Severity of Wind Turbine Generator Speed Peaks in Response to Particular Gusts. *2022 American Control Conference (ACC)*. [doi:10.23919/ACC53348.2022.9867404](https://doi.org/10.23919/ACC53348.2022.9867404)
- <a id="ref162"></a>[162] Kaminski et al. (2023). Parked aeroelastic field rotor response for a 20% scaled demonstrator of a 13‐MW downwind turbine. *Wind Energy*. [doi:10.1002/we.2794](https://doi.org/10.1002/we.2794)
- <a id="ref163"></a>[163] Kaminski et al. (2023). Gravo-aeroelastically-scaled demonstrator field tests to represent blade response of a flexible extreme-scale downwind turbine. *Renewable Energy*. [doi:10.1016/j.renene.2023.119217](https://doi.org/10.1016/j.renene.2023.119217)

### <a id="pubs-98"></a>98 - Engie La Haute Borne (7)
- <a id="ref164"></a>[164] Li et al. (2020). Short-term wind power forecasting based on support vector machine with improved dragonfly algorithm. *Journal of Cleaner Production*. [doi:10.1016/j.jclepro.2019.118447](https://doi.org/10.1016/j.jclepro.2019.118447)
- <a id="ref165"></a>[165] Li et al. (2021). Using enhanced crow search algorithm optimization-extreme learning machine model to forecast short-term wind power. *Expert Systems with Applications*. [doi:10.1016/j.eswa.2021.115579](https://doi.org/10.1016/j.eswa.2021.115579)
- <a id="ref166"></a>[166] Perr-Sauer et al. (2021). OpenOA: An Open-Source Codebase For Operational Analysis of Wind Farms. *Journal of Open Source Software*. [doi:10.21105/joss.02171](https://doi.org/10.21105/joss.02171)
- <a id="ref167"></a>[167] Dao (2022). On Wilcoxon rank sum test for condition monitoring and fault detection of wind turbines. *Applied Energy*. [doi:10.1016/j.apenergy.2022.119209](https://doi.org/10.1016/j.apenergy.2022.119209)
- <a id="ref168"></a>[168] Ewees et al. (2022). HBO-LSTM: Optimized long short term memory with heap-based optimizer for wind power forecasting. *Energy Conversion and Management*. [doi:10.1016/j.enconman.2022.116022](https://doi.org/10.1016/j.enconman.2022.116022)
- <a id="ref169"></a>[169] Liu et al. (2024). A novel deep learning-based evolutionary model with potential attention and memory decay-enhancement strategy for short-term wind power point-interval forecasting. *Applied Energy*. [doi:10.1016/j.apenergy.2024.122785](https://doi.org/10.1016/j.apenergy.2024.122785)
- <a id="ref170"></a>[170] Gijón et al. (2026). Prediction of wind turbines power with physics-informed neural networks and evidential uncertainty quantification. *Engineering Applications of Artificial Intelligence*. [doi:10.1016/j.engappai.2025.113331](https://doi.org/10.1016/j.engappai.2025.113331)

### <a id="pubs-99"></a>99 - Levenmouth Turbine (10)
- <a id="ref171"></a>[171] Chatterjee & Dethlefs (2020). Temporal Causal Inference in Wind Turbine SCADA Data Using Deep Learning for Explainable AI. *Journal of Physics: Conference Series*. [doi:10.1088/1742-6596/1618/2/022022](https://doi.org/10.1088/1742-6596/1618/2/022022)
- <a id="ref172"></a>[172] Chatterjee & Dethlefs (2020). A Dual Transformer Model for Intelligent Decision Support for Maintenance of Wind Turbines. *2020 International Joint Conference on Neural Networks (IJCNN)*. [doi:10.1109/IJCNN48605.2020.9206839](https://doi.org/10.1109/IJCNN48605.2020.9206839)
- <a id="ref173"></a>[173] Lin & Liu (2020). Wind power forecasting of an offshore wind turbine based on high-frequency SCADA data and deep learning neural network. *Energy*. [doi:10.1016/j.energy.2020.117693](https://doi.org/10.1016/j.energy.2020.117693)
- <a id="ref174"></a>[174] Lin et al. (2020). Wind power prediction based on high-frequency SCADA data along with isolation forest and deep learning neural networks. *International Journal of Electrical Power & Energy Systems*. [doi:10.1016/j.ijepes.2020.105835](https://doi.org/10.1016/j.ijepes.2020.105835)
- <a id="ref175"></a>[175] McKinnon et al. (2020). Comparison of New Anomaly Detection Technique for Wind Turbine Condition Monitoring Using Gearbox SCADA Data. *Energies*. [doi:10.3390/en13195152](https://doi.org/10.3390/en13195152)
- <a id="ref176"></a>[176] McKinnon et al. (2021). Investigation of Isolation Forest for Wind Turbine Pitch System Condition Monitoring Using SCADA Data. *Energies*. [doi:10.3390/en14206601](https://doi.org/10.3390/en14206601)
- <a id="ref177"></a>[177] Chatterjee & Dethlefs (2022). Automated Question-Answering for Interactive Decision Support in Operations & Maintenance of Wind Turbines. *IEEE Access*. [doi:10.1109/ACCESS.2022.3197167](https://doi.org/10.1109/ACCESS.2022.3197167)
- <a id="ref178"></a>[178] Hanifi et al. (2022). Offshore Wind Power Forecasting—A New Hyperparameter Optimisation Algorithm for Deep Learning Models. *Energies*. [doi:10.3390/en15196919](https://doi.org/10.3390/en15196919)
- <a id="ref179"></a>[179] Zhang et al. (2022). Short-term offshore wind power forecasting - A hybrid model based on Discrete Wavelet Transform (DWT), Seasonal Autoregressive Integrated Moving Average (SARIMA), and deep-learning-based Long Short-Term Memory (LSTM). *Renewable Energy*. [doi:10.1016/j.renene.2021.12.100](https://doi.org/10.1016/j.renene.2021.12.100)
- <a id="ref180"></a>[180] Rutyna (2025). Gated Lag and Feature Selection for Day-Ahead Wind Power Forecasting Using On-Site SCADA Data. *Wind*. [doi:10.3390/wind5040028](https://doi.org/10.3390/wind5040028)

## Other Resources:
**Data portals & platforms**
- [IEA Task 43](https://iea-wind.org/task43/task-43-open-data/) - IEA Wind task on digitalization & open data
- [DOE Wind Data Hub](https://wdh.energy.gov) - US DOE wind data repository (e.g. NREL SUMR-D, Flatirons)
- [Open Energy Data Initiative (OEDI)](https://data.openei.org) - incl. NREL gearbox condition monitoring vibration benchmark
- [NREL Wind AI Bench](https://registry.opendata.aws/nrel-pds-windai/) - ML benchmark data on AWS (mostly simulation/flow data, not SCADA)
- [WeDoWind](https://www.wedowind.ch) - platform hosting wind data challenges (e.g. EDP, Winji, Hill of Towie)

**Open-source tools for SCADA analysis**
- [NREL OpenOA](https://github.com/NREL/OpenOA) - operational analysis of wind plants (AEP, losses, yaw); uses La Haute Borne as example data
- [NREL FLASC](https://github.com/NREL/flasc) - wind farm SCADA analysis, incl. wake steering evaluation
- [RES wind-up](https://github.com/resgroup/wind-up) - uplift analysis for turbine upgrades (used for Hill of Towie)
- [Fraunhofer IEE EnergyFaultDetector](https://github.com/AEFDI/EnergyFaultDetector) - framework for early fault detection in energy assets

## Usage
[![Star History Chart](https://api.star-history.com/svg?repos=sltzgs/OpenWindSCADA&type=Date)](https://star-history.com/#sltzgs/OpenWindSCADA&Date)
