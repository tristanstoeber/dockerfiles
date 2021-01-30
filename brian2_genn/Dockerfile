FROM gpu-jupyter:latest

USER root
RUN apt-get update
RUN apt-get install -yq dvipng
RUN apt-get install -yq texlive-full

RUN wget https://developer.download.nvidia.com/compute/cuda/repos/ubuntu1804/x86_64/cuda-ubuntu1804.pin
RUN mv cuda-ubuntu1804.pin /etc/apt/preferences.d/cuda-repository-pin-600
RUN wget https://developer.download.nvidia.com/compute/cuda/11.0.3/local_installers/cuda-repo-ubuntu1804-11-0-local_11.0.3-450.51.06-1_amd64.deb
RUN dpkg -i cuda-repo-ubuntu1804-11-0-local_11.0.3-450.51.06-1_amd64.deb
RUN apt-key add /var/cuda-repo-ubuntu1804-11-0-local/7fa2af80.pub
RUN apt-get update
RUN apt-get -y install cuda

USER jovyan

RUN pip install tqdm
RUN pip install brian2genn

RUN wget https://github.com/genn-team/genn/archive/4.3.1.tar.gz
RUN tar -xzf 4.3.1.tar.gz && rm 4.3.1.tar.gz

ENV PATH=$PATH:$/home/jovyan/genn-4.3.1/bin

# hacky trick to ensure nvcc is available for genn
#RUN ln -s /usr/bin/ /usr/local/cuda/bin


