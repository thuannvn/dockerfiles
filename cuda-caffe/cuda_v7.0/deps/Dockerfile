# Start with cuDNN base image
FROM kaixhin/cudnn:7.0
MAINTAINER Kai Arulkumaran <design@kaixhin.com>

# Install git, bc and dependencies
RUN apt-get update && apt-get install -y \
  git \
  bc \
  cmake \
  libatlas-base-dev \
  libatlas-dev \
  libboost-all-dev \
  libopencv-dev \
  libprotobuf-dev \
  libgoogle-glog-dev \
  libgflags-dev \
  protobuf-compiler \
  libhdf5-dev \
  libleveldb-dev \
  liblmdb-dev \
  libsnappy-dev \
  python-dev \
  python-pip \
  python-numpy \
  gfortran > /dev/null

# Clone Caffe repo and move into it
RUN cd /root && git clone https://github.com/BVLC/caffe.git && cd caffe && \
# Install python dependencies
  cat python/requirements.txt | xargs -n1 pip install
