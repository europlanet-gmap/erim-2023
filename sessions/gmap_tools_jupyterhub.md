# GMAP tools: JupyterHub and Base mapping

Objectives:

- To share GMAP's Jupyter-Hub/-Lab setup
  * Attract users to our instance
  * Attract contributors to repo

Roadmap:

- Present Jupyter-Lab (ISIS/ASP/GISPY) setup
- Present Jupyter-Hub architecture & features
- Exemplify usage with Angelo's notebook
- Exemplify usage with (NPT) mosaic
- Exemplify usage with Mars-Craters

## Jupyter-Lab for planetary sciences
[ISIS]: https://github.com/DOI-USGS/ISIS3
[ASP]: https://github.com/NeoGeographyToolkit/StereoPipeline
[GDAL]: https://gdal.org/
[docker-isis]: https://github.com/europlanet-gmap/docker-isis3

One of the challenges we have as planetary data scientists is the setting up of a data processing environment.
The challenge regards installation and configuration of tools that demand some level of technical computing knowledge,
in particular, system administration knowledge.
Such tools, for instance, are the Integrated Software for Imagers and Spectrometers ([ISIS][]), Ames Sterio Pipeline ([ASP][]),
Geographical Data Abstraction Library ([GDAL][]), and modern Python data science stack.

Having issues to set up a working data processing environment hinders researchers' productivity, and can be detrimental
to data reproducibility since different software versions and configuration options can change results.
The scenarion is particularly sensitive when we consider the multiple systems data analysts will use during their research:
personal laptop, work computer, and cloud machines. Ideally, all those workstations have the same software so the focus
stays on the data and methods of analysis.

All in all, either because software installation is complex or on the debuging of software and data problems,
issues involving planetary data processing setups consume a considerable amount of time in the production
of scientific results.

To address this challenge -- or issue -- we, at GMAP, set up Docker containers with the main and most complex software
libraries we use in our everyday data analysis. Those containers run Jupyter-Lab servers as to provide a high-level
interface -- today's standard in many data analysis environments. The following software are highlighted in our containers:

- ISIS
- ASP
- GDAL
- Python libraries
  * Geopandas
  * Shapely
  * Kalarisis
  * Rasterio
  * Scipy
  * Xarray
  * _and others_

Such containers can be found, ready-to-use, in GMAP's DockerHub repository. And their definitions (ie, Dockerfiles),
for eventual customizations, in GMAP's GitHub [docker-isis][] public repository.

### How to use it

TBD

## GMAP Jupyter-Hub

TBD
