ARG BASE_IMAGE_TAG=latest
FROM quay.io/jupyter/tensorflow-notebook:${BASE_IMAGE_TAG}

USER root

RUN apt-get update && \
    apt-get install -y --no-install-recommends \
    gdal-bin && \
    rm -rf /var/lib/apt/lists/*

USER $NB_UID

RUN pip install -v --no-cache-dir \
    'opencv-python' \
    'geopandas' \
    'shapely' \
    'rasterio' \
    'folium' \
    'MetPy' && \
    fix-permissions "${CONDA_DIR}" && \
    fix-permissions "/home/${NB_USER}"