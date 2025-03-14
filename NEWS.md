# discretewq (development version)

* Added `DOP` water quality data.
* Updated baystudy dataset.

# discretewq 2.4.0

* Added temperature and conductivity to `USGS_CAWSC`
* Added DO and pH data to all surveys that collect this data. `USGS_SFBS` collects both calculated (from a sensor) and discrete DO, so we used discrete DO up to 2016 and calculated DO afterwards to mirror the methodological change that occurred in the `EMP` survey in 2016. 
* Updated to newest EMP data with some historical data issues fixed. 
* Added NCRO laboratory and water quality data
* Added bottom conductivity to `twentymm`, `baystudy`, `SDO`, `FMWT`, and `STN`
* Added turbidity to `EMP`, `FMWT`, and `STN`
* Fixed timezones for `SDO` data. SDO times are reported in PST but had incorrectly been imported as local time (PST/PDT). Now, they are imported as Etc/GMT+8 and then converted to America/Los_Angeles to correspond to the other surveys.
* Updated STN, FMWT, EDSM, DJFMP, SLS, Suisun, EMP, USGS_SFBS, USGS_CAWSC, YBFMP, SKT, 20mm, baystudy, and SDO datasets
* Removed rows from `FMWT` and `STN` datasets that did not contain any water quality information

# discretewq 2.3.2

* Fixing error where `YBFMP` Secchi data was in meters. Converted it to cm for consistency with other surveys. 
* Adding `Secchi_estimated` variable to `FMWT` data

# discretewq 2.3.1

# discretewq 2.3.0

* Changed the name of the `USGS` survey to `USGS_SFBS` to avoid confusion with the new `USGS_CAWSC` survey.
* Added USGS_CAWSC data.

# discretewq 2.2.0

* Add reporting limits (RLs) to EMP data.
* Updated STN data to newest version with 2021 data

# discretewq 2.1.0

* Added nutrient data to EMP and USGS datasets.

# discretewq 2.0.0

* Added the Yolo Bypass Fish Monitoring Program data
* Added Stockton Dissolved Oxygen survey as an additional data source
* Removed duplicated water quality data from suisun data
* Added Smelt Larva Survey as an additional data source
* Tweaked the wq function interface to force users to specify data sources, in preparation for adding more sources.
* Updated the DJFMP, EDSM, EMP, FMWT, SKT, STN, USGS, 20mm, Suisun datasets to their latest version

# discretewq 1.1.0

* Fixed timezones for EMP data. EMP times are reported in PST but had incorrectly been imported as local time (PST/PDT). Now, they are imported as Etc/GMT+8 and then converted to America/Los_Angeles to correspond to the other surveys.

# discretewq 1.0.1

# discretewq 1.0.0

* Publishing to link with data publication.

# discretewq 0.2.0

* Fixing one tide value of 0 from SKT by converting it to NA. 

# discretewq 0.1.0

* Undoing previous DJFMP change and now retaining all DJFMP data (except duplicates at the same date and time)
* Changing EDSM station variable to reflect each unique random 'site' so it is possible to identify replicate tows at the same location
* Tweaked USBR data to retain the average sample time across all depths (previously it used the earliest sample time).
* Tweaked DJFMP data to keep the datapoint closest to noon of each day (previously it was averaging across all time points)
* Added conductivity data from EDSM and DJFMP after 06/01/2019 when it was standardized to specific conductivity
* Added a `NEWS.md` file to track changes to the package.
