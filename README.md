# tcd_calib (code in construction)

# Towards Improving Calibration in Object Detection Under Domain Shift (Accepted @NeurIPS22)

# Paper Link
Here is the arXiv link: http://arxiv.org/abs/2209.07601

# Project Page
Here is the web-link: http://im.itu.edu.pk/towards-improving-calibration/

The increasing use of deep neural networks in safety-critical applications requires the trained models to be well-calibrated. Most current calibration techniques address classification problems while focusing on improving calibration on in-domain predictions. Little to no attention is paid towards addressing calibration of visual object detectors which occupy similar space and importance in many decision making systems. In this paper, we study the calibration of current object detection models, particularly under domain shift. To this end, we first introduce a  plug-and-play train-time calibration loss for object detection. It can be used as an auxiliary loss function to improve detector's calibration. Second, we devise a new uncertainty quantification mechanism for object detection which can implicitly calibrate the commonly used self-training based domain adaptive detectors. We include in our study both single-stage and two-stage object detectors. We demonstrate that our loss improves calibration for both in-domain and out-of-domain detections with notable margins. Finally, we show the utility of our techniques in calibrating the domain adaptive object detectors in diverse domain shift scenarios.

![alt text](https://github.com/akhtarvision/tcd_calib/blob/main/fig1-a_img.png)

Reliability diagrams. Top row: DNN-based detector (FCOS) trained using task-specific loss. Bottom row: Ours, trained with adding the proposed TCD loss.


![alt text](https://github.com/akhtarvision/tcd_calib/blob/main/calib_qual.jpg)

Visual depiction of calibration results for out-of-domain detections with one-stage detector (left column) and one-stage detector trained with our TCD loss (right column)

<!-- # Info
Details and Code coming soon -->


