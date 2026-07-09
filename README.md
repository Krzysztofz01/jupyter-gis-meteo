# Jupyter GIS Meteo

This repository contains the code needed to build customized **Jupyter** containers, which, in addition to machine learning tools, include Python libraries and CLI tools useful for:
- image processing, analysis and classification,
- working with spatial data and GIS technologies,
- working with meteorological data.

## Requirements
To build the images **Docker** or **Podman** needs to be installed. To run the build scripts **[Task](https://taskfile.dev/)** is required. The *Taskfile.yml* needs to be adjusted to select the installed container tool and adjust image versions.

## Images

### jupyter-pytorch-gis-meteo

The image is based on [jupyter/pytorch-notebook](https://quay.io/repository/jupyter/pytorch-notebook). The image is extended with:
- GDAL (CLI tool)
- opencv-python
- geopandas
- shapely
- rasterio
- folium
- MetPy

To build the image run:
```sh
task build:pytorch
``` 
This command will create a new image with a current date and latest tag. By default the lastest base image is used - this can be adjusted via the *Taskfile.yml*.

### jupyter-tensorflow-gis-meteo

The image is based on [jupyter/tensorflow-notebook](https://quay.io/repository/jupyter/tensorflow-notebook). The image is extended with:
- GDAL (CLI tool)
- opencv-python
- geopandas
- shapely
- rasterio
- folium
- MetPy

To build the image run:
```sh
task build:tensorflow
``` 
This command will create a new image with a current date and latest tag. By default the lastest base image is used - this can be adjusted via the *Taskfile.yml*.

## Resources

[Jupyter Docker Stacks Documentation](https://jupyter-docker-stacks.readthedocs.io/en/latest/using/selecting.html#)