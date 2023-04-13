# BRCA_Clonal_Resist_Project
Breast cancer clonal endocrine therapy resistance project

#### Efstathios-Iason Vlachavas
###### DKFZ-Division of Molecular Genome Analysis (B050)
###### Efstathios-Iason.Vlachavas@dkfz-heidelberg.de

[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.7780930.svg)](https://doi.org/10.5281/zenodo.7780930)

# OVERVIEW OF THE PROJECT

*We barcoded endocrine therapy sensitive cell lines (MCF7 and T47D) and rendered them resistant to commonly applied first line endocrine therapeutics (Tamoxifen and estrogen deprivation). Next, we isolated single cell clones of endocrine therapy resistant populations and subjected clonal cell lines to RNA-Seq and Phosphoproteomics profiling*.

## Small overview of the complete project framework (created with BioRender.com)

![1) Deconvolution of complex cell pools using a single-cell spotter.
2) Characterization of single cell clones using phenotypic assays, RNA-Seq and Mass-Spectrometry. Subsequent determination of pathway, TF and kinase activities.
3) Target and clinical validation using inhibitor treatment and the CPTAC-BRCA cohort. ](./Overview_PhD.png)


#### NOTE: *Core* parts of this tutorial are also part of the broader DKFZ-B050 lab project related to "*Breast cancer clonal endocrine therapy resistance project*"


## Description

## Notes on data acquisition and cohort definition

Metadata utilization
-Complete raw data along with the relevant clinical information (i.e. alternative sample names) has been deposited to the EGA archive [EGAS00001007123].

RNASeq data
- The analysis starts essentially with the DGE list object including raw counts, gene annotation and sample phenotype information.
- Further methodological details on the complete analysis are included in the accompanied.Rmd file & Materials & Methods section of the manuscript.

Phosproproteomics data
- Likewise, the bioinformatics workflow begins with the raw phosphoproteomics intensities stored in a *PhosphoExperiment object* (SummarizedExperiment class). Further information is pinpointed in the respective .Rmd file & Materials & Methods section of the manuscript.

## Important R packages that need to be installed for reproducing the analysis:

```r

packages = c(
    "edgeR",
    "circlize",
    "ComplexHeatmap"
    "tidyverse",
    "decoupleR",
    "OmnipathR",
    "limma",
    "PhosR",
    "vsn"
    "org.Hs.eg.db",
    "ggplot2",
    "forcats",
    "DOSE",
    "clusterProfiler",
    "enrichplot",
    "msigdbr",
    "enrichplot"
)

if(!requireNamespace("BiocManager")) {
    install.packages("BiocManager")
}

library(BiocManager)

for(p in packages) {
    if(!requireNamespace(p)) {
        install(p)
    }
}

```
## Implementation

- The user just needs to download/clone the respective github repository;
- For example `git clone https://github.com/Jasonmbg/BRCA_Clonal_Resist_Project.git

## Session Info 

```r
sessionInfo()
R version 4.1.0 (2021-05-18)
Platform: x86_64-w64-mingw32/x64 (64-bit)
Running under: Windows 10 x64 (build 19044)

Matrix products: default

locale:
[1] LC_COLLATE=English_United States.1252  LC_CTYPE=English_United States.1252   
[3] LC_MONETARY=English_United States.1252 LC_NUMERIC=C                          
[5] LC_TIME=English_United States.1252    

attached base packages:
[1] stats4    stats     graphics  grDevices utils     datasets  methods   base     

other attached packages:
 [1] dorothea_1.6.0        enrichplot_1.14.2     progeny_1.16.0        edgeR_3.36.0         
 [5] DOSE_3.20.1           clusterProfiler_4.2.2 org.Hs.eg.db_3.14.0   AnnotationDbi_1.56.2 
 [9] IRanges_2.28.0        S4Vectors_0.32.4      Biobase_2.54.0        BiocGenerics_0.40.0  
[13] OmnipathR_3.2.8       decoupleR_2.1.6       limma_3.50.3          forcats_0.5.2        
[17] stringr_1.5.0         dplyr_1.0.10          purrr_0.3.5           readr_2.1.3          
[21] tidyr_1.2.1           tibble_3.1.8          ggplot2_3.4.0         tidyverse_1.3.2   

```

## Acknowledgements

Lukas Beumers

Luisa Schwarzmüller

Dominic Helm

Stefan Wiemann

#### In addition, we would like to thank Julio Saez-Rodriguez's group (https://github.com/saezlab) for support and suggestions regarding the robust implementation of their respective computational tools and prior knowledge databases;


