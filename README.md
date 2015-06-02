# R package containing TCGA data

Make sure you have [rtools](http://cran.r-project.org/bin/windows/Rtools/) installed on your computer.

<h5> Installation of the `RTCGA.data` package: </h5>
Install the latest version of **RTCGA.data** from Bioconductor:
```{Ruby}
# not there yet
```
or use:
```{Ruby}
if (!require(devtools)) {
    install.packages("devtools")
    require(devtools)
}
install_github("mi2-warsaw/RTCGA.data")
```

<h5> The list of available datasets: </h5>
```{Ruby}
library(RTCGA.data)
?clinical
?rnaseq
```

# RTCGA.data package is based on RTCGA package

Project is (will be) supported by [Travis CI](https://travis-ci.org/) and [waffle.io](https://waffle.io/).

<h5> Installation of the `RTCGA` package: </h5>
To get started, install the latest version of **RTCGA** from Bioconductor:
```{Ruby}
# not there yet
```
or use:
```{Ruby}
if (!require(devtools)) {
    install.packages("devtools")
    require(devtools)
}
install_github("MarcinKosinski/RTCGA")
```
