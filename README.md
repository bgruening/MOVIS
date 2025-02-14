![movis_logo_banner](./Source/images/movis_logo_banner.png)
[![Build status](https://github.com/AAnzel/MOVIS/actions/workflows/main.yml/badge.svg)](https://github.com/AAnzel/MOVIS/actions/workflows/main.yml)
![Docker Image Version (latest by date)](https://img.shields.io/docker/v/aanzel/movis)
![Docker Image Size (latest by date)](https://img.shields.io/docker/image-size/aanzel/movis)
![GitHub issues](https://img.shields.io/github/issues-raw/AAnzel/MOVIS)
![GitHub](https://img.shields.io/github/license/AAnzel/MOVIS)

---
# MOVIS

**Exploratory data analysis and visualization tool for time-series multi-omics data sets.**


## Manuscript

This tool is created for the following paper:

***"MOVIS: A Multi-Omics Software Solution for Multi-modal Time-Series Clustering, Embedding, and Visualizing Tasks"*** by Aleksandar Anžel, Dominik Heider, and Georges Hattab

Please cite the paper as:
```latex
@article{ANZEL20221044,
title = {MOVIS: A multi-omics software solution for multi-modal time-series clustering, embedding, and visualizing tasks},
journal = {Computational and Structural Biotechnology Journal},
volume = {20},
pages = {1044-1055},
year = {2022},
issn = {2001-0370},
doi = {https://doi.org/10.1016/j.csbj.2022.02.012},
url = {https://www.sciencedirect.com/science/article/pii/S2001037022000526},
author = {Aleksandar Anžel and Dominik Heider and Georges Hattab},
keywords = {Time-series, Multi-omics, Visualization, Data exploration, Temporal multi-omics, Longitudinal multi-omics},
abstract = {Thanks to recent advances in sequencing and computational technologies, many researchers with biological and/or medical backgrounds are now producing multiple data sets with an embedded temporal dimension. Multi-modalities enable researchers to explore and investigate different biological and physico-chemical processes with various technologies. Motivated to explore multi-omics data and time-series multi-omics specifically, the exploration process has been hindered by the separation introduced by each omics-type. To effectively explore such temporal data sets, discover anomalies, find patterns, and better understand their intricacies, expertise in computer science and bioinformatics is required. Here we present MOVIS, a modular time-series multi-omics exploration tool with a user-friendly web interface that facilitates the data exploration of such data. It brings into equal participation each time-series omic-type for analysis and visualization. As of the time of writing, two time-series multi-omics data sets have been integrated and successfully reproduced. The resulting visualizations are task-specific, reproducible, and publication-ready. MOVIS is built on open-source software and is easily extendable to accommodate different analytical tasks. An online version of MOVIS is available under https://movis.mathematik.uni-marburg.de/ and on Docker Hub (https://hub.docker.com/r/aanzel/movis).}
}
```

[![DOI](./Source/images/movis_doi.svg)](https://www.sciencedirect.com/science/article/pii/S2001037022000526?via%3Dihub)

---
Abstract:

> Thanks to recent advances in sequencing and computational technologies, many researchers with biological and/or medical backgrounds are now producing multiple data sets with an embedded temporal dimension. Multi-modalities enable researchers to explore and investigate different biological and physico-chemical processes with various technologies. Motivated to explore multi-omics data and time-series multi-omics specifically, the exploration process has been hindered by the separation introduced by each omics-type. To effectively explore such temporal data sets, discover anomalies, find patterns, and better understand their intricacies, expertise in computer science and bioinformatics is required. Here we present MOVIS, a modular time-series multi-omics exploration tool with a user-friendly web interface that facilitates the data exploration of such data. It brings into equal participation each time-series omic-type for analysis and visualization. As of the time of writing, two time-series multi-omics data sets have been integrated and successfully reproduced. The resulting visualizations are task-specific, reproducible, and publication-ready. MOVIS is built on open-source software and is easily extendable to accommodate different analytical tasks. An online version of MOVIS is available under https://movis.mathematik.uni-marburg.de/ and on Docker Hub (https://hub.docker.com/r/aanzel/movis).


## Dependancy

The code is written in Python 3.8.11 and tested on Linux with the following libraries installed:

|Library|Version|
|---|---|
|altair|4.1.0|
|altair_saver|0.5.0|
|biopython|1.78|
|gensim|4.0.1|
|numpy|1.21.2|
|pandas|1.3.5|
|scikit-learn|1.0.2|
|scipy|1.7.3|
|streamlit|1.5.1|
|protobuf|3.19.1|
|python-levenshtein|0.12.2|
|click|7.1.2|

## Data
The data used in the **Example 1** comes from the following paper:

> **Integration of time-series meta-omics data reveals how microbial ecosystems respond to disturbance**, Herold, M., Martínez Arbas, S., Narayanasamy, S. et al. Nat Commun 11, 5281(2020).
https://doi.org/10.1038/s41467-020-19006-2.

It is stored at [Data/cached/example_1/](./Data/cached/example_1) in either a raw format or as a [pickle](https://docs.python.org/3/library/pickle.html) object.

The data used in the **Example 2** comes from the following paper:

> **Short- and Long-Term Transcriptomic Responses of Escherichia coli to Biocides: a Systems Analysis**, Merchel Piovesan Pereira, B., Wang, X., & Tagkopoulos, I. (2020). Applied and environmental microbiology, 86(14), e00708-20.
https://doi.org/10.1128/AEM.00708-20.

It is stored at [Data/cached/example_2/](./Data/cached/example_2) in a raw format.


## Code
|Script|Description|
|---|---|
|[Source/](./Source/)|contains all scripts necessary to run the tool.
|[Source/main.py](./Source/main.py)|contains the code that builds the main layout and connects all pages.
|[Source/home.py](./Source/home.py)|contains the code that builds the home page.
|[Source/example_1.py](./Source/example_1.py)|contains the code that builds the example 1 page.
|[Source/example_2.py](./Source/example_2.py)|contains the code that builds the example 2 page.
|[Source/case_study.py](./Source/case_study.py)|contains the code that builds the case study page.
|[Source/upload.py](./Source/upload.py)|contains the code that builds the upload page.
|[Source/common.py](./Source/common.py)|contains the code with functions shared by all pages.
|[Source/visualize.py](./Source/visualize.py)|contains the code with functions that create various visualizations present in this tool.

## Getting started
Check out our [Wiki page](https://github.com/AAnzel/MOVIS/wiki) for detailed information about MOVIS and how to use it.

## Installation & Running
### Stable
The easiest way to install the tool is to use our latest Docker image:

```
docker pull aanzel/movis:latest
docker run --publish 8501:8501 --detach --name movis aanzel/movis:latest
```


You can start using the tool by opening a web browser and typing in [http://localhost:8501/](http://localhost:8501/) as the address. If you run the docker container, you have to use the IP address or hostname instead of localhost.

### Unstable
*Caution! Use at your own risk!*

You could also clone this repository, build a docker container yourself, and run it locally. This is not recommended as we might introduce unstable features that might not end in the next release of MOVIS. Below is a sequence of instructions (for Linux-based systems) to run the **unstable** version of MOVIS:

```
git clone https://github.com/AAnzel/MOVIS.git
cd MOVIS
docker build -t movis-local:unstable .
docker run --publish 8501:8501 --detach --name movis movis-local:unstable
```

You can start using the tool by opening a web browser and typing in [http://localhost:8501/](http://localhost:8501/) as the address. If you run the docker container, you have to use the IP address or hostname instead of localhost.

## License

Licensed under the GNU General Public License, Version 3.0 ([LICENSE](./LICENSE) or https://www.gnu.org/licenses/gpl-3.0.en.html)

### Contribution

Any contribution intentionally submitted for inclusion in the work by you, shall be licensed under the GNU GPLv3.
