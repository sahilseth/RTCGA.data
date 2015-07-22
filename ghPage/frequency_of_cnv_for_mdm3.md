# Using `RTCGA` package to estimate a frequency of MDM2 duplications based on CNV data
Przemyslaw Biecek  
`r Sys.Date()`  



# RTCGA.cnv package

You need RTCGA.cnv package to use CNV scores.


```r
if (!require(devtools)) {
    install.packages("devtools")
    require(devtools)
}
if (!require(RTCGA.cnv)) {
    install_github("mi2-warsaw/RTCGA.data", subdir = "RTCGA.cnv")
    require(RTCGA.cnv)
}
```


# MDM2

To get scores for all cancers for selected gene or region one should use
the get.region.cnv.score() function.

For example, MDM2 is located on chromosome 12 positions 69240000-69200000.


```r
MDM2.scores <- get.region.cnv.score(chr="12", start=69240000, stop=69200000)

# only one per patient
MDM2.scores$Sample <- substr(MDM2.scores$Sample, 1, 12)
MDM2.scores <- MDM2.scores[!duplicated(MDM2.scores$Sample),]
```

Let's see where there are more than 3 copies of MDM2


```r
cutoff <- log(3)/log(2)-1
MDM2cuted <- cut(MDM2.scores$Segment_Mean, c(0, cutoff, Inf), labels = c("<= 3", "> 3"))
```

And now we can calculate number of cases with <= or >3 copies od MDM2 in each cancer type.


```r
table(MDM2.scores$cohort, MDM2cuted)
```

```
              MDM2cuted
               <= 3 > 3
  ACC.cnv        64   1
  BLCA.cnv      288   1
  BRCA.cnv      739   3
  CESC.cnv      205   0
  CHOL.cnv       29   0
  COAD.cnv      339   0
  COADREAD.cnv  109   0
  DLBC.cnv       35   0
  ESCA.cnv      122   1
  GBM.cnv       404   8
  GBMLGG.cnv    359   0
  HNSC.cnv      369   0
  KICH.cnv       49   0
  KIPAN.cnv     519   1
  KIRC.cnv        0   0
  KIRP.cnv        0   0
  LAML.cnv      125   0
  LGG.cnv         0   0
  LIHC.cnv      260   1
  LUAD.cnv      372   1
  LUSC.cnv      341   3
  MESO.cnv       60   0
  OV.cnv        373   3
  PAAD.cnv      134   0
  PCPG.cnv      112   0
  PRAD.cnv      347   0
  READ.cnv        0   0
  SARC.cnv      147   3
  SKCM.cnv      351   0
  STAD.cnv      307   3
  STES.cnv        0   0
  TGCT.cnv      109   0
  THCA.cnv      350   0
  THYM.cnv       89   0
  UCEC.cnv      378   0
  UCS.cnv        30   0
  UVM.cnv        60   0
```
