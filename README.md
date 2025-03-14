
<!-- README.md is generated from README.Rmd. Please edit that file -->

# discretewq

<!-- badges: start -->

[![R-CMD-check](https://github.com/InteragencyEcologicalProgram/discretewq/actions/workflows/R-CMD-check.yaml/badge.svg)](https://github.com/InteragencyEcologicalProgram/discretewq/actions/workflows/R-CMD-check.yaml)
[![Codecov test
coverage](https://codecov.io/gh/InteragencyEcologicalProgram/discretewq/branch/main/graph/badge.svg)](https://codecov.io/gh/InteragencyEcologicalProgram/discretewq?branch=main)
[![DOI](https://zenodo.org/badge/309747392.svg)](https://zenodo.org/badge/latestdoi/309747392)
[![Data
DOI](https://img.shields.io/badge/Data%20publication%20DOI-10.6073/pasta/8dbd29c8c22f3295bbc5d3819fb51d00-blue.svg)](https://portal.edirepository.org/nis/mapbrowse?scope=edi&identifier=731)
<!-- badges: end -->

The goal of discretewq is to integrate discrete water quality data from
the San Francisco Estuary.

## Installation

You can install the latest version from [GitHub](https://github.com/)
with:

``` r
# install.packages("devtools")
devtools::install_github("InteragencyEcologicalProgram/discretewq")
```

## Usage

To obtain the full integrated water quality dataset

``` r
library(discretewq)

Data <- wq(
  Sources = c(
    "20mm",
    "Baystudy",
    "DJFMP",
    "DOP",
    "EDSM",
    "EMP",
    "FMWT",
    "NCRO",
    "SDO",
    "SKT",
    "SLS",
    "STN",
    "Suisun",
    "USBR",
    "USGS_CAWSC",
    "USGS_SFBS",
    "YBFMP"
  )
)

str(Data)
#> tibble [358,969 × 79] (S3: tbl_df/tbl/data.frame)
#>  $ Source                       : chr [1:358969] "20mm" "20mm" "20mm" "20mm" ...
#>  $ Station                      : chr [1:358969] "504" "519" "809" "901" ...
#>  $ Latitude                     : num [1:358969] 38.1 38.1 38.1 38 38 ...
#>  $ Longitude                    : num [1:358969] -122 -122 -122 -122 -122 ...
#>  $ Field_coords                 : logi [1:358969] FALSE FALSE FALSE FALSE FALSE FALSE ...
#>  $ Date                         : POSIXct[1:358969], format: "1997-05-03" "1997-05-03" ...
#>  $ Datetime                     : POSIXct[1:358969], format: "1997-05-03 07:50:00" "1997-05-03 08:36:00" ...
#>  $ Depth                        : num [1:358969] 7.62 3.05 12.19 2.44 7.62 ...
#>  $ Tide                         : chr [1:358969] "Ebb" "Ebb" "Flood" "Flood" ...
#>  $ Secchi                       : num [1:358969] 16 13 63 78 90 48 58 70 68 74 ...
#>  $ Temperature                  : num [1:358969] 17.1 17.2 18.8 19.1 20 20.2 20.6 20.6 21.4 19.5 ...
#>  $ Conductivity                 : num [1:358969] 1490 652 239 250 276 311 302 339 321 230 ...
#>  $ Conductivity_bottom          : num [1:358969] 1949 1174 248 251 275 ...
#>  $ Notes                        : chr [1:358969] NA NA NA NA ...
#>  $ Temperature_bottom           : num [1:358969] NA NA NA NA NA NA NA NA NA NA ...
#>  $ DissolvedOxygen              : num [1:358969] NA NA NA NA NA NA NA NA NA NA ...
#>  $ Salinity                     : num [1:358969] 0.747 0.316 0.113 0.118 0.131 ...
#>  $ pH                           : num [1:358969] NA NA NA NA NA NA NA NA NA NA ...
#>  $ TurbidityFNU                 : num [1:358969] NA NA NA NA NA NA NA NA NA NA ...
#>  $ Chlorophyll                  : num [1:358969] NA NA NA NA NA NA NA NA NA NA ...
#>  $ DissolvedOxygen_bottom       : num [1:358969] NA NA NA NA NA NA NA NA NA NA ...
#>  $ Microcystis                  : num [1:358969] NA NA NA NA NA NA NA NA NA NA ...
#>  $ Chlorophyll_Sign             : chr [1:358969] NA NA NA NA ...
#>  $ DissolvedOxygenPercent       : num [1:358969] NA NA NA NA NA NA NA NA NA NA ...
#>  $ DissolvedOxygenPercent_bottom: num [1:358969] NA NA NA NA NA NA NA NA NA NA ...
#>  $ pH_bottom                    : num [1:358969] NA NA NA NA NA NA NA NA NA NA ...
#>  $ TurbidityNTU                 : num [1:358969] NA NA NA NA NA NA NA NA NA NA ...
#>  $ TurbidityNTU_bottom          : num [1:358969] NA NA NA NA NA NA NA NA NA NA ...
#>  $ TurbidityFNU_bottom          : num [1:358969] NA NA NA NA NA NA NA NA NA NA ...
#>  $ Pheophytin_Sign              : chr [1:358969] NA NA NA NA ...
#>  $ Pheophytin                   : num [1:358969] NA NA NA NA NA NA NA NA NA NA ...
#>  $ TotAlkalinity_Sign           : chr [1:358969] NA NA NA NA ...
#>  $ TotAlkalinity                : num [1:358969] NA NA NA NA NA NA NA NA NA NA ...
#>  $ TotAmmonia_Sign              : chr [1:358969] NA NA NA NA ...
#>  $ TotAmmonia                   : num [1:358969] NA NA NA NA NA NA NA NA NA NA ...
#>  $ DissAmmonia_Sign             : chr [1:358969] NA NA NA NA ...
#>  $ DissAmmonia                  : num [1:358969] NA NA NA NA NA NA NA NA NA NA ...
#>  $ DissBromide_Sign             : chr [1:358969] NA NA NA NA ...
#>  $ DissBromide                  : num [1:358969] NA NA NA NA NA NA NA NA NA NA ...
#>  $ DissCalcium_Sign             : chr [1:358969] NA NA NA NA ...
#>  $ DissCalcium                  : num [1:358969] NA NA NA NA NA NA NA NA NA NA ...
#>  $ TotChloride_Sign             : chr [1:358969] NA NA NA NA ...
#>  $ TotChloride                  : num [1:358969] NA NA NA NA NA NA NA NA NA NA ...
#>  $ DissChloride_Sign            : chr [1:358969] NA NA NA NA ...
#>  $ DissChloride                 : num [1:358969] NA NA NA NA NA NA NA NA NA NA ...
#>  $ DissNitrateNitrite_Sign      : chr [1:358969] NA NA NA NA ...
#>  $ DissNitrateNitrite           : num [1:358969] NA NA NA NA NA NA NA NA NA NA ...
#>  $ DOC_Sign                     : chr [1:358969] NA NA NA NA ...
#>  $ DOC                          : num [1:358969] NA NA NA NA NA NA NA NA NA NA ...
#>  $ TOC_Sign                     : chr [1:358969] NA NA NA NA ...
#>  $ TOC                          : num [1:358969] NA NA NA NA NA NA NA NA NA NA ...
#>  $ DON_Sign                     : chr [1:358969] NA NA NA NA ...
#>  $ DON                          : num [1:358969] NA NA NA NA NA NA NA NA NA NA ...
#>  $ TON_Sign                     : chr [1:358969] NA NA NA NA ...
#>  $ TON                          : num [1:358969] NA NA NA NA NA NA NA NA NA NA ...
#>  $ DissOrthophos_Sign           : chr [1:358969] NA NA NA NA ...
#>  $ DissOrthophos                : num [1:358969] NA NA NA NA NA NA NA NA NA NA ...
#>  $ TotPhos_Sign                 : chr [1:358969] NA NA NA NA ...
#>  $ TotPhos                      : num [1:358969] NA NA NA NA NA NA NA NA NA NA ...
#>  $ DissSilica_Sign              : chr [1:358969] NA NA NA NA ...
#>  $ DissSilica                   : num [1:358969] NA NA NA NA NA NA NA NA NA NA ...
#>  $ TDS_Sign                     : chr [1:358969] NA NA NA NA ...
#>  $ TDS                          : num [1:358969] NA NA NA NA NA NA NA NA NA NA ...
#>  $ TSS_Sign                     : chr [1:358969] NA NA NA NA ...
#>  $ TSS                          : num [1:358969] NA NA NA NA NA NA NA NA NA NA ...
#>  $ VSS_Sign                     : chr [1:358969] NA NA NA NA ...
#>  $ VSS                          : num [1:358969] NA NA NA NA NA NA NA NA NA NA ...
#>  $ TKN_Sign                     : chr [1:358969] NA NA NA NA ...
#>  $ TKN                          : num [1:358969] NA NA NA NA NA NA NA NA NA NA ...
#>  $ Secchi_estimated             : logi [1:358969] NA NA NA NA NA NA ...
#>  $ Sample_depth_surface         : num [1:358969] NA NA NA NA NA NA NA NA NA NA ...
#>  $ Sample_depth_bottom          : num [1:358969] NA NA NA NA NA NA NA NA NA NA ...
#>  $ Salinity_bottom              : num [1:358969] 0.989 0.582 0.117 0.119 0.13 ...
#>  $ Sample_depth_nutr_surface    : num [1:358969] NA NA NA NA NA NA NA NA NA NA ...
#>  $ MonthYear                    : POSIXct[1:358969], format: "1997-05-01" "1997-05-01" ...
#>  $ Year                         : num [1:358969] 1997 1997 1997 1997 1997 ...
#>  $ StationID                    : chr [1:358969] "20mm 504" "20mm 519" "20mm 809" "20mm 901" ...
#>  $ Month                        : num [1:358969] 5 5 5 5 5 5 5 5 5 5 ...
#>  $ Season                       : chr [1:358969] "Spring" "Spring" "Spring" "Spring" ...
```

## Data publication

The dataset is also [published on the Environmental Data
Initiative](https://portal.edirepository.org/nis/mapbrowse?scope=edi&identifier=731),
where you can find detailed metadata. This static version of the dataset
corresponds to version 2.4.0 of the R package ([archived on
zenodo](https://zenodo.org/record/8008212)).

## Data sources

Battey, M. and S. Perry. 2023. Interagency Ecological Program: Discrete
water quality monitoring in the Sacramento-San Joaquin Bay-Delta,
collected by the Environmental Monitoring Program, 1975-2022 ver 9.
Environmental Data Initiative.
[doi:10.6073/pasta/a306956e3ebdc78348c2df8d05cd2ccb](https://portal.edirepository.org/nis/metadataviewer?packageid=edi.458.9)

CDFW. 2024. Bay Study data.
<https://filelib.wildlife.ca.gov/Public/BayStudy/Access_Database/>.

CDFW. 2023a. Fall Midwater Trawl data.
<https://filelib.wildlife.ca.gov/public/TownetFallMidwaterTrawl/FMWT%20Data/>.

CDFW. 2023b. Summer Townet data.
<https://filelib.wildlife.ca.gov/public/TownetFallMidwaterTrawl/TNS%20MS%20Access%20Data/TNS%20data/>.

CDWR. 2023. Water Quality Evaluation Section, North Central Region
Office.
<https://wdl.water.ca.gov/waterdatalibrary/WaterQualityDataLib.aspx>.

Cloern, J. E., and T. S. Schraga. 2016. USGS Measurements of Water
Quality in San Francisco Bay (CA), 1969-2015 (ver. 3.0 June 2017). U. S.
Geological Survey data release.
[doi:https://doi.org/10.5066/F7TQ5ZPR](https://doi.org/10.5066/F7TQ5ZPR)

Interagency Ecological Program (IEP), S. Lesmeister, and J. Rinde. 2020.
Interagency Ecological Program: Discrete dissolved oxygen monitoring in
the Stockton Deep Water Ship Channel, collected by the Environmental
Monitoring Program, 1997-2018. ver2. Environmental Data Initiative.
[doi:10.6073/PASTA/3268530C683726CD430C81894FFAD768](https://portal.edirepository.org/nis/metadataviewer?packageid=edi.276.2)

Interagency Ecological Program (IEP), L. Damon, and A. Chorazyczewski.
2021a. Interagency Ecological Program San Francisco Estuary 20mm Survey
1995 - 2021. ver 4. Environmental Data Initiative.
[doi:10.6073/pasta/32de8b7ffbe674bc6e79dbcd29ac1cc2](https://portal.edirepository.org/nis/metadataviewer?packageid=edi.535.4)

Interagency Ecological Program (IEP), L. Damon, and A. Chorazyczewski.
2021b. Interagency Ecological Program San Francisco Estuary Spring
Kodiak Trawl Survey 2002 - 2021. ver 4. Environmental Data Initiative.
[doi:10.6073/pasta/f0e2916f4a026f3f812a0855cee74a8d](https://portal.edirepository.org/nis/metadataviewer?packageid=edi.527.4)

Interagency Ecological Program (IEP), L. Damon, T. Tempel, and A.
Chorazyczewski. 2021c. Interagency Ecological Program San Francisco
Estuary Smelt Larva Survey 2009 – 2021. ver 4. Environmental Data
Initiative.
[doi:10.6073/pasta/8e1ceb1c02fbc8b0ba7a6b58229109f2](https://portal.edirepository.org/nis/metadataviewer?packageid=edi.534.4)

Interagency Ecological Program (IEP), C. Pien, J. Adams, and N. Kwan.
2021d. Interagency Ecological Program: Zooplankton catch and water
quality data from the Sacramento River floodplain and tidal slough,
collected by the Yolo Bypass Fish Monitoring Program, 1998-2018. ver 2.
Environmental Data Initiative.
[doi:10.6073/pasta/baad532af96cba1d58d43b89c08ca081](https://portal.edirepository.org/nis/metadataviewer?packageid=edi.494.2)

Interagency Ecological Program (IEP), R. McKenzie, J. Speegle, A.
Nanninga, J.R. Cook, J. Hagen, and B. Mahardja. 2022a. Interagency
Ecological Program: Over four decades of juvenile fish monitoring data
from the San Francisco Estuary, collected by the Delta Juvenile Fish
Monitoring Program, 1976-2021. ver 9. Environmental Data Initiative.
[doi:10.6073/pasta/30a3232084be9c936c976fbb6b31c5a2](https://portal.edirepository.org/nis/metadataviewer?packageid=edi.244.9)

Interagency Ecological Program (IEP), C. Pien, and N. Kwan. 2022b.
Interagency Ecological Program: Fish catch and water quality data from
the Sacramento River floodplain and tidal slough, collected by the Yolo
Bypass Fish Monitoring Program, 1998-2021. ver 3. Environmental Data
Initiative.
[doi:10.6073/pasta/f5c4362f4a1f370723e2b9113432909f](https://portal.edirepository.org/nis/metadataviewer?packageid=edi.233.3)

O’Rear, T., J. Durand, and P. Moyle. 2022. Suisun Marsh Fish Study.
<https://watershed.ucdavis.edu/project/suisun-marsh-fish-study>.

Schraga, T. S., E. S. Nejad, C. A. Martin, and J. E. Cloern. 2020. USGS
measurements of water quality in San Francisco Bay (CA), beginning in
2016 (ver. 3.0, March 2020). U. S. Geological Survey data release.
[doi:https://doi.org/10.5066/F7D21WGF](https://doi.org/10.5066/F7D21WGF)

Schultz, A. A. and A. J. Kalmbach. 2023. Directed Outflow Project Lower
Trophic Study ver 4. Environmental Data Initiative.
[doi:10.6073/pasta/86a01140eb3bb756ee9f7f8dab8aefc4](https://portal.edirepository.org/nis/metadataviewer?packageid=edi.1187.4).

United States Fish and Wildlife Service, T. Senegal, R. Mckenzie, J.
Speegle, B. Perales, D. Bridgman, K. Erly, S. Staiger, A. Arrambide, and
M. Gilbert. 2022. Interagency Ecological Program and US Fish and
Wildlife Service: San Francisco Estuary Enhanced Delta Smelt Monitoring
Program data, 2016-2021 ver 8. Environmental Data Initiative.
[doi:10.6073/pasta/e1a540c161b7be56b941df50fd7b44c5](https://portal.edirepository.org/nis/metadataviewer?packageid=edi.415.8)

U.S. Geological Survey. 2022. USGS water data for the Nation: U.S.
Geological Survey National Water Information System database, accessed
October 21, 2022, at
[doi:10.5066/F7P55KJN](https://doi.org/10.5066/F7P55KJN)

USBR, R. Dahlgren, L. Loken, and E. Van Nieuwenhuyse. 2020. Monthly
vertical profiles of water quality in the Sacramento Deep Water Ship
Channel 2012-2019. <https://www.usbr.gov/mp/bdo/index.html>
