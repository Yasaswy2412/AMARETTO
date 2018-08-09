[//]: # (TODO: Bioconductor support?)
[//]: # (TODO: Some examples)

# AMARETTO

[![License](https://img.shields.io/badge/license-GPL-yellow.svg)](https://opensource.org/licenses/GPL-2.0)
[![Version](https://img.shields.io/badge/version-0.99.1-lightgrey.svg)]()

Capturing pancancer genetically and epigenetically driver genes.

## Table of Contents

- [Getting Started](#getting-started)
- [Introduction](#introduction)
- [References](#references)
- [Author Information](#author-information)
- [Citation](#citation)
- [License](#license)

## Getting Started

__Installation__

To install the _AMARETTO_ package, clone the GitHub directory:

```{bash, eval=FALSE}
// bash
git clone https://github.com/gevaertlab/AMARETTO
```
Then install the package from source within R.

```{r, eval=FALSE}
// R
install.packages("AMARETTO", repos = NULL, type="source")
```


__Loading__

To load the `AMARETTO` package in your R session:

```{r, eval=FALSE}
// R
library(AMARETTO)
```

__Help__ 

Detailed information on `AMARETTO` package functions can be obtained in the help files. For example, to view the help file for the function `AMARETTO` in a R session, use `?AMARETTO`.

## Introduction

This repository contains the code accompanying the manuscript ["Module analysis captures pancancer genetically and epigenetically deregulated cancer driver genes for smoking and antiviral response"](https://www.sciencedirect.com/science/article/pii/S2352396417304723).
We have developed an algorithm called AMARETTO to identify pancancer driver genes. AMARETTO integrates pancancer DNA copy number, DNA methylation, and gene expression data into modules to identify pancancer driver genes. 

The algorithm: 
* Step 1 identifies candidate cancer driver genes with tumor-specific DNA copy number or DNA methylation alterations compared to normal tissue. We used GISTIC to identify significantly and recurrently deleted or amplified regions in the genome. Similarly, we used MethylMix to identify recurrently hyper- or hypomethylated genes. 
* Step 2 identifies cancer driver genes by modeling the relationship between (epi)genomic and transcriptomic data on an individual gene basis.
* Step 3 uses the cancer driver genes identified from Step 2 and takes a global approach by dissecting global gene expression data into modules of co-expressed genes. Each module also has an associated regulatory program that connects the cancer driver genes from Step 1 with their downstream targets. This regulatory program is modeled using linear regression with elastic net regularization.
 
AMARETTO supports downloading and processing TCGA data from [Firehose](https://gdac.broadinstitute.org/).

## References

>Champion, M., Brennan, K., Croonenborghs, T., Gentles, A. J., Pochet, N., & Gevaert, O. (2018). Module Analysis Captures Pancancer Genetically and Epigenetically Deregulated Cancer Driver Genes for Smoking and Antiviral Response. EBioMedicine, 27, 156–166. doi:10.1016/j.ebiom.2017.11.028

## Author Information

<table>
  <tr>
    <th> Magali Champion </th>
    <th> Katie Planey </th>
    <th> Olivier Gevaert </th>
  </tr>
  <tr>
    <td colspan="3" align="center"> Stanford Center for Biomedical Informatics
    Department of Medicine </td>
  </tr>
  <tr>
  	<td colspan="3" align="center"> Department of Medicine </td>
  </tr>
  <tr>
  	<td colspan="3" align="center"> 1265 Welch Road </td>
  </tr>
  <tr>
  	<td colspan="3" align="center"> Stanford CA, 94305-5479 </td>
  </tr>
</table>

## Citation

If you use AMARETTO in your work, please cite:

> Champion, M., Brennan, K., Croonenborghs, T., Gentles, A. J., Pochet, N., & Gevaert, O. (2018). Module Analysis Captures Pancancer Genetically and Epigenetically Deregulated Cancer Driver Genes for Smoking and Antiviral Response. R package version 0.99.1.

> Gevaert O, Villalobos V, Sikic BI, Plevritis SK. Identification of ovarian cancer driver genes by using module network integration of multi-omics data. Interface Focus. 5(2) (2013)

## License

AMARETTO is licensed under the GPL-2 license. See the [LICENSE](https://github.com/gevaertlab/AMARETTO/LICENSE) for more information.