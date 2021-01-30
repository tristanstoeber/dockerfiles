FROM jupyter/datascience-notebook

USER root
RUN apt-get update
RUN apt-get install -yq dvipng
RUN apt-get install -yq texlive-full

USER jovyan

RUN pip install tqdm
RUN pip install brian2


