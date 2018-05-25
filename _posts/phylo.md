---
title: 'R-09: Get data and set working directory'
author: "Dev Paudel"
date: "May 25, 2018"
output:
      html_document:
        keep_md: true
---

#### Load package

```r
library(rotl)
```

#### Create and draw phylogeny
Create a list of species

```r
spp <- c("Cenchrus purpureus", "Cenchrus americanus", "Arabidopsis thaliana","Brachypodium distachyon", "Hordeum vulgare","Oryza sativa", "Panicum virgatum","Sorghum bicolor","Setaria italica","Triticum aestivum","Zea mays")
```

Resolve names
```r
taxa <- tnrs_match_names(spp, context_name = "Flowering plants") # resolve names
```

Create phylogeny
```r
tr <- tol_induced_subtree(ott_id(taxa), label="name")
```

Draw phylogeny
```r
plot(tr)
```
![](https://github.com/dpaudel/rbiology.github.io/tree/master/img/20180525_phylogeny.png)<!-- -->
