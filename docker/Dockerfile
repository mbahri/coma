FROM nvidia/cuda:8.0-cudnn6-runtime-ubuntu16.04

RUN apt update
RUN apt install -y python-pip python-virtualenv git vim wget
RUN apt install -y libboost-dev
RUN apt install -y python-dev python-pip cython python-numpy python-scipy python-matplotlib libopencv-dev python-opencv

RUN git clone https://github.com/MPI-IS/mesh.git
RUN git clone https://github.com/mbahri/coma.git

WORKDIR /mesh
RUN make
RUN make install

WORKDIR /coma
RUN pip install -r requirements.txt

WORKDIR /

CMD bash