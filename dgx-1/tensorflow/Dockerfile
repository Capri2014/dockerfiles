FROM nvcr.io/nvidia/tensorflow:17.07
MAINTAINER Fangchang Ma <fcma@mit.edu>

# ubuntu packages
RUN apt-get update && apt-get install -y \
  git \
  wget \ 
  unzip \ 
  vim \
  libhdf5-serial-dev hdf5-tools \
  libmatio2 

RUN apt-get -y build-dep python-matplotlib
RUN pip install h5py matplotlib lmdb

# git lfs
WORKDIR /root
RUN wget https://github.com/git-lfs/git-lfs/releases/download/v2.3.4/git-lfs-linux-amd64-2.3.4.tar.gz
RUN tar -xvzf git-lfs-linux-amd64-2.3.4.tar.gz 
WORKDIR /root/git-lfs-2.3.4
RUN ./install.sh

# environment
RUN git config --global credential.helper cache
WORKDIR /workspace
ENV OMP_NUM_THREADS=2
