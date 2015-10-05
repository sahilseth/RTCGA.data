# The family of R packages containing TCGA data

[Contribution: Adding a new package to the `RTCGA.data` family](https://github.com/mi2-warsaw/RTCGA.data/wiki/Contribution:-Adding-a-new-package-to-the-%60RTCGA.data%60-family)

Data packages submitted to Bioconductor

- [RTCGA.mutations](http://bioconductor.org/packages/3.2/data/experiment/html/RTCGA.mutations.html)
- [RTCGA.rnaseq](http://bioconductor.org/packages/3.2/data/experiment/html/RTCGA.rnaseq.html)
- [RTCGA.clinical](http://bioconductor.org/packages/3.2/data/experiment/html/RTCGA.clinical.html)

### Installation of packages from the `RTCGA.data` family: 

Make sure you have [rtools](http://cran.r-project.org/bin/windows/Rtools/) installed on your computer.

```{Ruby}
# packages that are published to devel version of Bioconductor
BiocInstaller::useDevel() # swiches to devel branchof Bioconductor
source("https://bioconductor.org/biocLite.R") # downloads bioClite function
biocLite("RTCGA.clinical") # installs a package
biocLite("RTCGA.rnaseq")
biocLite("RTCGA.mutations")


# packages not yet published to Bioconductor
if (!require(devtools)) {
   install.packages("devtools")
   require(devtools)
}
install_github("mi2-warsaw/RTCGA.data/PANCAN12")
install_github("mi2-warsaw/RTCGA.data/cnv")
```

<h5> The list of available datasets: </h5>
```{Ruby}
library(RTCGA.clinical)
library(RTCGA.rnaseq)
library(RTCGA.mutations)
library(RTCGA.PANCAN12)
library(RTCGA.cnv)
?clinical
?rnaseq
?mutations
?pancan12
?cnv
```

# Packages from the `RTCGA.data`-family are based on the `RTCGA` package


### Installation of the [`RTCGA`](https://github.com/MarcinKosinski/RTCGA) package: 
To get started, install the latest version of **RTCGA** from GitHub:

```{Ruby}
BiocInstaller::useDevel() # swiches to devel branchof Bioconductor
source("https://bioconductor.org/biocLite.R") # downloads bioClite function
biocLite("RTCGA") # installs a package
```

<h4> Authors: </h4>

>
> Marcin Kosiński, m.p.kosinski@gmail.com
>
> Przemysław Biecek, przemyslaw.biecek@gmail.com
>
