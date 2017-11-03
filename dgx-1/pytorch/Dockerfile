FROM nvcr.io/nvidia/pytorch:17.07
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
RUN pip install h5py
RUN pip install matplotlib

# get the latest pytorch
RUN pip uninstall torch -y
RUN pip install http://download.pytorch.org/whl/cu80/torch-0.2.0.post3-cp35-cp35m-manylinux1_x86_64.whl 
RUN pip install torchvision

# enviromnet
ENV OMP_NUM_THREADS=2
