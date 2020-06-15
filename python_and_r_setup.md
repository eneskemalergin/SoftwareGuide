# Setup for Python and R Co-existing Environment with Conda


## Setting up Anaconda
1. Install [anaconda](https://www.anaconda.com/distribution/) distribution.
2. Update conda to the current version: ```conda update -n base conda```
3. Update all packages to the latest version: ```conda update anaconda```

## Setting up Channels for Conda
Setup for channels is important to assign priority. The last channel to config is the highest priority.

- ```conda config --add channels conda-forge```
- ```conda config --add channels defaults```
- ```conda config --add channels r```
- ```conda config --add channels bioconda```

## Setting up R and RStudio with Conda
Installing R and Rstudio is possible with conda, this allows a seamless integration of R in jupyter-notebook. Also a use of R in python and python in R within the same notebook.
- Install base r: ```conda install -c bioconda R=3.6.1```
- Install [Rstudio](https://rstudio.com/products/rstudio/download/)
  - Rstudio command in terminial will open an Rstudio instance which finds the path to anaconda automatically.


## Installing Other useful R packages
### Ubuntu Libraries to be Installed
- ```sudo apt-get install libopenblas-base```
- ```sudo apt-get install libpng16-16```

### Bioconductor packages
- **EdgeR** - ```conda install -c bioconda bioconductor-edger```
- **DESeq2** - ```conda install -c bioconda bioconductor-deseq2```
- **sva** - ```conda install -c bioconda bioconductor-sva```
- **phetmap** - ```conda install -c bioconda r-pheatmap```
- **preprocessCore** - ```conda install -c bioconda bioconductor-preprocesscore```
  - A collection of pre-processing functions
- **clusterProfiler** - ```conda install -c bioconda bioconductor-clusterprofiler```
  - [Package github](https://github.com/YuLab-SMU/clusterProfiler)
  - [Package tutorial](https://yulab-smu.github.io/clusterProfiler-book/)
  - [Package documentation](https://guangchuangyu.github.io/software/clusterProfiler/documentation/)
- **RforProteomics** - ```conda install -c bioconda bioconductor-rforproteomics```
- **RforMassSpectrometry** - ```BiocManager::install("RforMassSpectrometry/RforMassSpectrometry")```
  - [Package tutorial](https://www.rformassspectrometry.org/)
  - [Package documentation](https://rformassspectrometry.github.io/RforMassSpectrometry/index.html)

### CRAN packages
- **Tidyverse** - ```conda install -c r r-tidyverse```
- **ggpubR** - ```conda install -c conda-forge r-ggpubr```
  - Publication ready plots
- **Plotly** - ```conda install -c conda-forge r-plotly```
- **circlize** - ```conda install -c conda-forge r-circlize```
  - Circular visualization package.
  - [Package github](https://github.com/jokergoo/circlize)
  - [Package tutorial](https://jokergoo.github.io/circlize_book/book/)
- **FactoExtra** - ```conda install -c conda-forge r-factoextra```
  - Multivariate data analsis package for visualizing
  - [Package github](https://github.com/kassambara/factoextra)
  - [Package documentation](https://rpkgs.datanovia.com/factoextra/index.html)
- **devtools** - ```conda install -c conda-forge r-devtools```
- **heplots** - ```conda install -c conda-forge r-heplots```
  - Visualizing Hypothesis Tests in Multivariate Linear Models

### Github Packages
To install github packages to the R environment within anaconda requires setting options before installing them with devtools:
- Within R: ```options(unzip = "internal")```
- Within terminal: ```sudo ln -s /bin/tar /bin/gtar```
- **ampvis2** - ```install_github("MadsAlbertsen/ampvis2")```
  - Tools for visualizing amplicon data
- **patchwork** - ```install_github("thomasp85/patchwork")```
  - Package to make combining plots simpler.


## Installing other useful Python packages

- **BioPython** - ```conda install -c bioconda biopython```
- **feather** - ```conda install -c conda-forge feather-format```
- **Altair** - ```conda install -c conda-forge altair vega_datasets```
- **fastcluster** - ```conda install -c conda-forge fastcluster```
- **PtitPrince** - ```conda install -c pog87 ptitprince```
- **adjusttext** - ```conda install -c phlya adjusttext```
- **Plotly** - ```conda install -c plotly plotly plotly_express```
- **Dash** - ```conda install -c plotly dash jupyter-dash```
- **Cufflinks** - ```conda install -c conda-forge cufflinks-py```
- **Prince** - ```pip install prince```
  - Library for factor anaysis
  
## Installing Node.js for jupyterlab
- ```conda install -c nodejs```

### Installing JupyterLab extensions
Enable the extensions tab in the jupyterLab settings, which makes installing extensions easier. Many of the extension could be installed through the jupyterlab.

- **Table of Contents** - ```jupyter labextension install @jupyterlab/toc```
- **NBextension Configurator** - ```conda install -c conda-forge jupyter_nbextensions_configurator```
- **Contrib NBextennsions** - ```conda install -c conda-forge jupyter_contrib_nbextensions```
