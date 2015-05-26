# R package containing TCGA data
Marcin Kosiński  
`r Sys.Date()`  



<h5> Installation of the `RTCGA` package: </h5>
To get started, install the latest version of **RTCGA** from Bioconductor:

```r
# not there yet
```
or use:

```r
if (!require(devtools)) {
    install.packages("devtools")
    require(devtools)
}
install_github("MarcinKosinski/RTCGA")
```
Make sure you have [rtools](http://cran.r-project.org/bin/windows/Rtools/) installed on your computer.


<h5> Installation of the `RTCGA.data` package: </h5>
Install the latest version of **RTCGA.data** from Bioconductor:

```r
# not there yet
```
or use:

```r
if (!require(devtools)) {
    install.packages("devtools")
    require(devtools)
}
install_github("mi2-warsaw/RTCGA.data")
```

<h5> The list of available datasets: </h5>

```r
library(RTCGA.data)
?clinical
?rnaseq
```
