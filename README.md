# Raspberry Pi Benchmarking with YuNet

## Model
The model used to benchmark the different Raspberry Pi boards was [face_detection_yunet_2023mar.onnx](models/face_detection_yunet_2023mar.onnx) from [OpenCV Zoo](https://github.com/opencv/opencv_zoo) (git tag [4.10.0](https://github.com/opencv/opencv_zoo/tree/4.10.0)). This is a face detection model based on [libfacedetection](https://github.com/ShiqiYu/libfacedetection) by [Shiqi Yu](https://github.com/ShiqiYu).

[OpenCV Zoo](https://github.com/opencv/opencv_zoo) is licensed under the [Apache-2.0 license](models/LICENSE).

## Image
The test image [NH 96919-KN.jpeg](images/NH%2096919-KN.jpeg) was of Commodore Grace Hopper and is from the [Navy History and Heritage Command](https://www.history.navy.mil/content/history/nhhc/our-collections/photography/numerical-list-of-images/nhhc-series/nh-series/NH-96000/NH-96919-KN.html) website.

- Title: Commodore Grace M. Hopper, USNR
- Caption: Official portrait photograph of Commodore Grace M. Hopper, USNR. Original photo number DN-SC-84-05970.
- Accession #: NH
- Catalog #: NH 96919-KN
- Copyright Owner: Defense Imagery
- Original Creator: James S. Davis
- Original Date: 1984-01-20
- Original Format: Color photograph

## Raspberry Pi
### Hardware
Four different Raspberry Pi boards were tested:
- [Raspberry Pi 5 Model B Rev 1.0](https://www.raspberrypi.com/products/raspberry-pi-5/)
- [Raspberry Pi 4 Model B Rev 1.1](https://www.raspberrypi.com/products/raspberry-pi-4-model-b/)
- [Raspberry Pi Zero 2 W Rev 1.0](https://www.raspberrypi.com/products/raspberry-pi-zero-2-w/)
- [Raspberry Pi 3 Model B Rev 1.2](https://www.raspberrypi.com/products/raspberry-pi-3-model-b/)

### Operating System
[Raspberry Pi OS Lite](https://downloads.raspberrypi.com/raspios_lite_arm64/images/raspios_lite_arm64-2024-11-19/)
- Release date: November 19th 2024
- System: 64-bit
- Kernel version: 6.6
- Debian version: 12 (bookworm)
- Size: 438MB

## Benchmarking
The model was tested at four different resolutions:
- 480x640 (VGA)
- 240x320 (QVGA)
- 120x160 (QQVGA)
- 60x80

<p align="center">
    <img src="data/multi_resolution_yunet_test.jpg" width="1200"/>
</p>

## Maximum CPU Frequency (w/o Overclocking)
Except for [CPU Frequency vs Inference Time](#cou-frequency-vs-inference-time), none of the Raspberry Pi's were overclocked and the max allowed CPU frequency was used for each board (listed in the table below).

| Raspberry Pi         | CPU Freq. [MHz] |
|:--------------------:|:---------------:|
| Raspberry Pi 5       | 2400            |
| Raspberry Pi 4       | 1500            |
| Raspberry Pi 3       | 1200            |
| Raspberry Pi Zero 2W | 1000            |

## Resolution vs Inference Time
- Max allowed CPU Frequency (w/o overclocking)
- Max # of CPUs: 4

<p align="center">
    <img src="data/rpi_yunet_resolution.jpg" width="1000"/>
</p>

## CPU Frequency vs Inference Time
- Resolution: 480x640
- Max # of CPUs: 4

<p align="center">
    <img src="data/rpi_yunet_cpu_freq.jpg" width="1000"/>
</p>

## Number of CPU Cores vs Inference Time
- Max allowed CPU Frequency (w/o overclocking)
- Resolution: 480x640

<p align="center">
    <img src="data/rpi_yunet_cpu_num.jpg" width="1000"/>
</p>
