FROM nvidia/cuda:11.4.2-cudnn8-runtime-ubuntu20.04
WORKDIR /app
ARG DEBIAN_FRONTEND=noninteractive
RUN apt update
RUN apt -y install libgl1-mesa-glx libegl1-mesa libxrandr2 libxrandr2 libxss1 libxcursor1 libxcomposite1 libasound2 libxi6 libxtst6 curl ffmpeg git nano gnupg2 libsm6 wget unzip libxcb-icccm4 libxkbcommon-x11-0 libxcb-keysyms1 libxcb-icccm4 libxcb-render0 libxcb-render-util0 libxcb-image0
RUN apt install -y python3 python3-pip
RUN ln -s /usr/bin/python3 /usr/bin/python

RUN git clone https://github.com/iperov/DeepFaceLive.git

RUN python -m pip install --upgrade pip
RUN python -m pip install onnxruntime-gpu==1.11.1 numpy==1.21.6 h5py numexpr protobuf==3.20.1 opencv-python==4.5.5.64 opencv-contrib-python==4.5.5.64 pyqt6==6.3.0 onnx==1.11.0 torch==1.10.0 torchvision==0.11.1

WORKDIR /app/DeepFaceLive
COPY example.sh example.sh
CMD ./example.sh
#####
