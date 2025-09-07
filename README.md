


# DroneTrackRT

**DroneTrackRT** is a real-time drone tracking system leveraging the power of the YOLO object detection framework and NVIDIA TensorRT, optimized for the Jetson Nano platform.  

This project provides a state-of-the-art solution for drone detection and tracking, designed for high precision and real-time performance in aerial surveillance applications.

---

## 📖 Table of Contents
- [Introduction](#introduction)
- [Key Features](#key-features)
- [Installation Guide](#installation-guide)
- [Configuration & Dependencies](#configuration--dependencies)
- [Model Customization & Training](#model-customization--training)
- [Model Conversion](#model-conversion)
- [Testing & Validation](#testing--validation)
- [License](#license)
- [Support](#support)
- [Additional Resources](#additional-resources)

---

## 🛰️ Introduction

**DroneTrackRT** delivers a robust solution for real-time drone monitoring.  
It is designed for applications such as **airspace security, drone traffic management, and surveillance**, where reliability and low latency are critical.  

By combining the efficiency of **YOLOv5** with **NVIDIA TensorRT acceleration** on Jetson Nano, the system achieves an outstanding balance between **speed** and **accuracy**.

---

## 🚀 Key Features

- **Real-Time Drone Detection & Tracking**  
  - Powered by YOLOv5, optimized with TensorRT.  

- **Advanced Motion Handling**  
  - Reliable tracking even with fast maneuvers or sudden trajectory changes.  

- **NVIDIA Jetson Nano Integration**  
  - Fully optimized for Jetson Nano with CUDA and TensorRT acceleration.  

- **Live Data Visualization**  
  - Real-time display of tracking results for situational awareness.  

- **Multi-Camera Compatibility**  
  - Supports various cameras compatible with Jetson Nano.  

- **Flexible YOLO Models**  
  - Choose the YOLO version that best fits your application (v5–v7).  

---

## ⚙️ Installation Guide

### System & Software Prerequisites

Update and install required dependencies:

```bash
sudo apt-get update
sudo apt-get install -y liblapack-dev libblas-dev gfortran libfreetype6-dev \
libopenblas-base libopenmpi-dev libjpeg-dev zlib1g-dev
sudo apt-get install -y python3-pip
pip install -r requirements.txt
````

### Common Issues

* **Missing dependencies** → Install manually using `apt-get` or `pip`.
* **Installation failure** → Ensure Jetson Nano is updated to the latest JetPack release.

---

## 🔧 Configuration & Dependencies

* **Jetson Nano Developer Kit**: JetPack 4.6 \[L4T 32.6.1]
* **Core libraries**:

  * CUDA 10.2.300
  * cuDNN 8.2.1.32
  * TensorRT 8.0.1.6
  * OpenCV 4.1.1
  * PyTorch v1.10 + torchvision v0.11.1
  * Python 3.6+
  * YOLOv5–YOLOv7

### Additional Installations

* **PyCUDA**

```bash
export PATH=/usr/local/cuda-10.2/bin${PATH:+:${PATH}}
export LD_LIBRARY_PATH=/usr/local/cuda-10.2/lib64:$LD_LIBRARY_PATH
pip install pycuda --user
```

* **Seaborn**

```bash
sudo apt install python3-seaborn
```

📌 For PyTorch & torchvision installation on Jetson Nano, follow [this NVIDIA forum guide](https://forums.developer.nvidia.com/t/pytorch-for-jetson/72048).

---

## 🧠 Model Customization & Training

To train your own YOLO model:

1. Collect and label drone datasets.
2. Configure YOLO model parameters.
3. Run training with:

```bash
python train.py
```

---

## 🔄 Model Conversion

Convert a `.pt` model into a TensorRT `.engine` format for optimized inference:

```bash
cd JetsonYoloV5
python3 gen_wts.py -w yolov5s.pt -o yolov5s.wts
```

Then follow TensorRT build instructions to generate the `.engine` file.

---

## ✅ Testing & Validation

Run the main application:

```bash
python3 app.py
```

This will start real-time drone detection and display live results.

---

## 📜 License

This project is distributed under the **MIT License**.
See the [LICENSE](LICENSE) file for details.

---

## 💬 Support

For questions or issues, please open a ticket in the **Issues** section of this repository.

---

## 📚 Additional Resources

* [mailrocketsystems/JetsonYolov5](https://github.com/mailrocketsystems/JetsonYolov5)
* [Running YOLOv5 with TensorRT on Jetson Nano (YouTube)](https://www.youtube.com/watch?v=ErWC3nBuV6k)
* [YOLOv5 TensorRT Object Detection on Jetson Nano (YouTube)](https://www.youtube.com/watch?v=-Vu65N1NRWw)

👉 Check out the **Rocket Systems** YouTube channel for more great demos.

