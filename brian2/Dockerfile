FROM jupyter/scipy-notebook

USER root
RUN apt-get update && apt-get install -yq dvipng

USER jovyan

RUN pip install tqdm
RUN pip install brian2genn