# Family of R packages containing TCGA data

Make sure you have [rtools](http://cran.r-project.org/bin/windows/Rtools/) installed on your computer.

<h5> Installation of packages from the `RTCGA.data` family : </h5>


```{Ruby}
if (!require(devtools)) {
    install.packages("devtools")
    require(devtools)
}
install_github("mi2-warsaw/RTCGA.data", subdir = paste0("RTCGA.", c("clinical", "rnaseq")))
```

<h5> The list of available datasets: </h5>
```{Ruby}
library(RTCGA.clinical)
library(RTCGA.rnaseq)
?clinical
?rnaseq
```

# Packages from the `RTCGA.data`-family are based on the `RTCGA` package


<h5> Installation of the `RTCGA` package: </h5>
To get started, install the latest version of **RTCGA** from Bioconductor:

```{Ruby}
if (!require(devtools)) {
    install.packages("devtools")
    require(devtools)
}
install_github("MarcinKosinski/RTCGA")
```

<h4> Authors: </h4>

>
> Marcin Kosiński, m.p.kosinski@gmail.com
>