FROM nvcr.io/nvidia/torch:17.07
MAINTAINER Fangchang Ma <fcma@mit.edu>

# ubuntu packages
RUN apt-get update && apt-get install -y \
  git \
  wget \ 
  unzip \ 
  vim \
  libhdf5-serial-dev hdf5-tools \
  libmatio2
#  tmux \
#  libopenblas-dev \
#  liblapack-dev
#  cython \
#  gnuplot 
  
# python packages
# RUN pip install h5py

# Torch packages
RUN git clone https://github.com/davek44/torch-hdf5.git /root/torch-hdf5
WORKDIR /root/torch-hdf5
RUN luarocks make
# RUN luarocks install hdf5
# RUN luarocks install torchx 
# RUN luarocks install torch
RUN luarocks install matio
# RUN luarocks install cunn
# RUN luarocks install cudnn
# RUN luarocks install nnx
# RUN luarocks install csvigo
# RUN luarocks install colormap

# enviromnet
ENV OMP_NUM_THREADS=2
WORKDIR /workspace
