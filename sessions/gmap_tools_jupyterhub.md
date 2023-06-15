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
[docker-isis3]: https://github.com/europlanet-gmap/docker-isis3

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
for eventual customizations, in GMAP's GitHub [docker-isis3][] public repository.

### How to use 
[gmap/isis]: https://hub.docker.com/r/gmap/isis

The Jupyter Lab/Notebook Docker images are ready to be used, when launched, the container starts a Jupyter-Lab server
at port "8000" (default) through which the user can access environment (with the above-mentioned software installed).

The images are provided at GMAP' Dockerhub [gmap/isis][] repository, 
[https://hub.docker.com/r/gmap/isis](https://hub.docker.com/r/gmap/isis), 
and the definition of the containers are in the project's GitHub repository,
[docker-isis3][], [https://github.com/europlanet-gmap/docker-isis3](https://github.com/europlanet-gmap/docker-isis3).

> Follow the instructions (aka, *docs*) in Git's repository to *build* and *run* your images.

Essentially, all we need to do is to download the docker image,
> ```bash
> docker pull gmap/isis:jupyter
> ```

This will take some time, it will download a couple of gigabytes and expand that into a ~5 gigabytes container image.

Then run it, binding container's port `8888` to host's `8888` and the directory with your data (for instance),
> ```bash
> docker run --name "jupyter-isis" -p "8888:8888" -v "/path/to/data:/home/jovyan/data" gmap/isis:jupyter
> ```

You can then open a new browser window and go to `http://localhost:8000`, you should see a Jupyter-Lab server.
If necessary, copy the "token" for user authentication from the log message printed by "jupyter-isis" in the terminal.

In Jupyter-Lab (or Notebook) interface, the left sidebar provides a view of the filesystem, we should see a `data` folder,
it is the sharing folder with "`/path/to/data`".

Once again, in this environment you'll find the software packages mentioned previously, ISIS, ASP, GDAL, Python libraries,
and some other command-line tools such as `git` and `vim`.

If you new to Jupyter Lab/Notebook, please have a look at [https://docs.jupyter.org/](https://docs.jupyter.org/).


#### Dependencies
[ISISDATA]: https://github.com/DOI-USGS/ISIS3/blob/dev/README.md#The-ISIS-Data-Area

ISIS relies on [ISISDATA][] to do many of its tasks but the multi-gigabyte dataset is *not* included in the container.
The user must first download "ISIS-DATA" (as explained in [https://github.com/DOI-USGS/ISIS3](https://github.com/DOI-USGS/ISIS3) 
and *share* it with the Docker container.


### Example 

Exemplify with Mars-Craters.


## GMAP Jupyter-Hub

TBD
