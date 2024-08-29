# Introduction

This repository reproduced [YOLOv5_JDE](https://github.com/xiaobin1231/YOLOv5_JDE) on python verison 3.8 and pytorch version 2.4.0, corrected the code based on training evaluation errors caused by version switching issues, and attached the MOT17/PRW/ETHZ/CUHKSYSU dataset that conforms to the JDE training method.

JDE is a fast and high-performance multiple-object tracker that learns the object detection task and appearance embedding task simutaneously in a shared neural network. Due to the recent release of YOLOv5, we replace the detector in JDE with YOLOv5 and achieve high performance on MOT Benchmark. For some reasons, 
we can't release our stronger version, but we hope this repo will help researches/engineers to develop more practical real-time MOT systems.

# Requirements
Just follow the environmnet configuration of [YOLOv5](https://github.com/ultralytics/yolov5).

## Install

  conda create -n yolov5jde python=3.8
  conda activate yolov5jde
  git clone https://github.com/Mercuryyu/yolov5_jde.git
  cd yolov5_jde
  pip install -r requirement.txt

## Dataset preparation

Just follow the [DATASET_ZOO](https://github.com/Zhongdao/Towards-Realtime-MOT/blob/master/DATASET_ZOO.md) of JDE. The attached dataset comes from here.

## Training

python train.py --cfg  models/yolov5_JDE.yaml

## Evaluation

python track.py --cfg ./models/yolov5_JDE.yaml --weights ./runs/exp/weights/best.pt

