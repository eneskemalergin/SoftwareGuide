# Setup for Python and R Co-existing Environment with Conda


## Setting up Anaconda
1. Install [anaconda](https://www.anaconda.com/distribution/) distribution.
2. Update conda to the current version: ```conda update -n base conda```
3. Update all packages to the latest version: ```conda update anaconda```

## Setting up Channels for Conda
Setup for channels is important to assign priority. The last channel to config is the highest priority.

- ```conda config --add channels defaults```
- ```conda config --add channels r```
- ```conda config --add channels bioconda```
- ```conda config --add channels conda-forge```

## Setting up R and RStudio with Conda
Installing R and Rstudio is possible with conda, this allows a seamless integration of R in jupyter-notebook. Also a use of R in python and python in R within the same notebook.
- Install base r: ```conda install r-base```
- Install r-essential(list of popular r-packages) ```conda install -c r r-essentials```
  - *Version can be specified in the installation*
- Install [Rstudio](https://rstudio.com/products/rstudio/download/)
  - Rstudio command in terminial will open an Rstudio instance which finds the path to anaconda automatically.

## Installing Other useful R packages
### CRAN packages
- **devtools** - ```install.packages("devtools")```
- **ggpubR** - ```install.packages("ggpubr")```
  - Publication ready plots
- **cowplots** - ```install.packages("cowplot")```
  - Streamlined plot theme and plot annotations for ggplot2
- **pathfindR** - ```install.packages("pathfindR")```
  - Package for enrichment analysis utilizing active subnetworks.
- **circlize** - ```install.packages("circlize")```
  - Circular visualization package.
  - [Package github](https://github.com/jokergoo/circlize)
  - [Package tutorial](https://jokergoo.github.io/circlize_book/book/)

### Github Packages
- **ampvis2** - ```install_github("MadsAlbertsen/ampvis2")```
  - Tools for visualizing amplicon data
- **patchwork** - ```install_github("thomasp85/patchwork")```
  - Package to make combining plots simpler.

### Bioconductor packages
Using Bioconductor requires ```BiocManager```.
- ```if (!requireNamespace("BiocManager", quietly = TRUE))```
- ```install.packages("BiocManager")```

- **clusterProfiler** - ```BiocManager::install("clusterProfiler")```
  - [Package github](https://github.com/YuLab-SMU/clusterProfiler)
  - [Package tutorial](https://yulab-smu.github.io/clusterProfiler-book/)
  - [Package documentation](https://guangchuangyu.github.io/software/clusterProfiler/documentation/)
- **RforMassSpectrometry** - ```BiocManager::install("RforMassSpectrometry/RforMassSpectrometry")```
  - [Package tutorial](https://www.rformassspectrometry.org/)
  - [Package documentation](https://rformassspectrometry.github.io/RforMassSpectrometry/index.html)
- **Limma** - ```BiocManager::install("limma")```
- **EdgeR** - ```BiocManager::install("edgeR")```
- **DESeq2** - ```BiocManager::install("DESeq2")```
- **sva** - ```BiocManager::install("sva")```
- **ComplexHeatmap** - ```BiocManager::install("ComplexHeatmap")```
  - Package to make complex heatmaps.
  - [Package github](https://github.com/jokergoo/ComplexHeatmap)
  - [Package tutorial](https://jokergoo.github.io/ComplexHeatmap-reference/book/)
- **preprocessCore** - ```BiocManager::install("preprocessCore")```
  - A collection of pre-processing functions
-
