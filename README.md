## tidycensus

[![Build Status](https://travis-ci.org/walkerke/tidycensus.svg?branch=master)](https://travis-ci.org/walkerke/tidycensus) ![CRAN Badge](http://www.r-pkg.org/badges/version/tidycensus)  ![CRAN Downloads](http://cranlogs.r-pkg.org/badges/tidycensus)

__tidycensus__ is an R package that allows users to interface with the US Census Bureau's decennial Census and five-year American Community APIs and return tidyverse-ready data frames, optionally with simple feature geometry included.  Install from CRAN with the following command: 

```r
install.packages("tidycensus")
```

## New in version 0.3: 

* Get an entire table of decennial Census or ACS data by supplying the table name.  For example, to get the entire ACS table __B01001__ from the 2016 1-year ACS (assuming here that you've already installed your Census API key with `census_api_key("KEY", install = TRUE)`: 

```
library(tidycensus)

df <- get_acs(geography = "state", table = "B01001", survey = "acs1", year = 2016)

```

The `table` parameter fetches a variable list from the Census Bureau website to perform table lookup.  To cache the variable list on your computer for faster use of the `table` parameter in the future, set `cache_table = TRUE` the first time you fetch a table for a particular dataset.  

## Why tidycensus? 

My work heavily involves the use of data from the US Census Bureau, and like many R users, I do most of my work within the __tidyverse__.  Beyond this, the __sf__ package now allows R users to work with spatial data in an integrated way with __tidyverse__ tools, and updates to the __tigris__ package provide access to Census boundary data as `sf` objects.  Recently, I've found myself writing the same routines over and over to get Census data ready for use with __tidyverse__ packages and __sf__.  This motivated me to wrap these functions in a package and open-source in case other R users find them useful.  

__tidycensus__ is designed to help R users get Census data that is pre-prepared for exploration within the __tidyverse__, and optionally spatially with __sf__.  To learn more about how the package works, I encourage you to read the following articles: 

* [Basic usage of __tidycensus__](https://walkerke.github.io/tidycensus/articles/basic-usage.html)
* [Spatial data in __tidycensus__](https://walkerke.github.io/tidycensus/articles/spatial-data.html)
* [Margins of error in the ACS](https://walkerke.github.io/tidycensus/articles/margins-of-error.html)

## Future development

To keep up with on-going development of __tidycensus__ and get even more examples of how to use the package, [subscribe to my email list by clicking here](http://eepurl.com/cPGKZD) (no spam, I promise!).  You'll also get updates on the development of my upcoming book with CRC Press, _Analyzing the US Census with R_.  

You can also follow my blog at https://walkerke.github.io.  

My development focus is on making the current datasets as accessible as possible; if you need other approaches or datasets, I recommend the [censusapi](https://github.com/hrecht/censusapi) and [acs](https://cran.r-project.org/package=acs) packages.

If you find this project useful, you can support package development in the following ways: 

* Hiring me as a consultant to help you use __tidycensus__ in your project, or hiring me to give a workshop on __tidycensus__ for your organization.  Please contact me at <kwalkerdata@gmail.com> if you are interested!
* Filing an issue - or even better, a pull request - at https://github.com/walkerke/tidycensus/issues.  

Note: This product uses the Census Bureau Data API but is not endorsed or certified by the Census Bureau.