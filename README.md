# Towards Improving Calibration in Object Detection Under Domain Shift (NeurIPS22)

# Paper Link
Here is the [link](https://openreview.net/pdf?id=a7YeDeacHpL)

# Abstract
Project Page: Here is the [web-link](http://im.itu.edu.pk/towards-improving-calibration/)

The increasing use of deep neural networks in safety-critical applications requires the trained models to be well-calibrated. Most current calibration techniques address classification problems while focusing on improving calibration on in-domain predictions. Little to no attention is paid towards addressing calibration of visual object detectors which occupy similar space and importance in many decision making systems. In this paper, we study the calibration of current object detection models, particularly under domain shift. To this end, we first introduce a  plug-and-play train-time calibration loss for object detection. It can be used as an auxiliary loss function to improve detector's calibration. Second, we devise a new uncertainty quantification mechanism for object detection which can implicitly calibrate the commonly used self-training based domain adaptive detectors.

![alt text](https://github.com/akhtarvision/tcd_calib/blob/main/fig1-a_img.png)

Reliability diagrams. Top row: DNN-based detector (FCOS) trained using task-specific loss. Bottom row: Ours, trained with adding the proposed TCD loss.

## Setup

This code is setup on:
Linux, CUDA>=10.1, Python>=3.8, PyTorch>=1.4.0, torchvision==0.2.1

Single GPU Quadro RTX 6000

## Installation

This implementation is based on [maskrcnn-benchmark](https://github.com/facebookresearch/maskrcnn-benchmark). See original maskrcnn-benchmark.

For complete installation, follow [here](INSTALL.md)

## Training and Evaluation
For VGG based implementation

### Training

To train, run the following command
```
python tools/train_net.py --config-file ./configs/sim10k_VGG_16_FPN_4x.yaml
```

### Evaluation
To evaluate, run the following command
```
python tools/test_net.py --config-file <CONFIG_PATH> MODEL.WEIGHT <WEIGHT_PATH>
```

## D-ECE 

For Detection Expected Calibration Error evaluation, follow the guidelines [here](https://pypi.org/project/netcal/)

## Qualitative

![alt text](https://github.com/akhtarvision/tcd_calib/blob/main/calib_qual.jpg)

Visual depiction of calibration results for out-of-domain detections with one-stage detector (left column) and one-stage detector trained with our TCD loss (right column)

## Citation

Please cite the following, if you find this work useful in your research:
```bibtex
@inproceedings{munir2022towards,
title={Towards Improving Calibration in Object Detection Under Domain Shift},
author={Muhammad Akhtar Munir and Muhammad Haris Khan and M. Saquib Sarfraz and Mohsen Ali},
booktitle={Advances in Neural Information Processing Systems},
year={2022},
}
```

## Acknowledgement

This codebase implementation is based on [FCOS](https://github.com/tianzhi0549/FCOS), [EPM](https://github.com/chengchunhsu/EveryPixelMatters) and [Detection Calibration](https://pypi.org/project/netcal/)


