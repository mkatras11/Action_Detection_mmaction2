# Spatiotemporal Action Detection

## Introduction
Detect human actions both in spatial and temporal dimensions using MMAction2.

MMAction2 is an open-source toolbox for video understanding based on PyTorch.
It is a part of the [OpenMMLab](https://openmmlab.com/) project.

## Installation

This project depends on [PyTorch](https://pytorch.org/), [MMCV](https://github.com/open-mmlab/mmcv), and [MMDetection](https://github.com/open-mmlab/mmdetection).
Below are some quick steps for installation:

```shell
conda create -n st_action_det python=3.8 
conda activate st_action_det
pip install torch==1.9.0+cu111 torchvision==0.10.0+cu111 -f https://download.pytorch.org/whl/torch_stable.html
pip3 install openmim
mim install mmcv-full
mim install mmdet 
git clone https://github.com/mkatras11/Action_Detection_mmaction2.git
pip install -r requirements.txt
```

## Methods and Datasets

<table style="margin-left:auto;margin-right:auto;font-size:1.3vw;padding:3px 5px;text-align:center;vertical-align:center;">
  <tr>
    <td colspan="5" style="font-weight:bold;">Supported Methods</td>
  </tr>
  <tr>
    <td><a href="https://github.com/mkatras11/Action_Detection_mmaction2/tree/main/configs/detection/acrn/README.md">ACRN</a> (ECCV'2018)</td>
    <td><a href="https://github.com/mkatras11/Action_Detection_mmaction2/tree/main/configs/detection/ava/README.md">SlowOnly+Fast R-CNN</a> (ICCV'2019)</td>
    <td><a href="https://github.com/mkatras11/Action_Detection_mmaction2/tree/main/configs/detection/ava/README.md">SlowFast+Fast R-CNN</a> (ICCV'2019)</td>
    <td><a href="https://github.com/mkatras11/Action_Detection_mmaction2/tree/main/configs/detection/lfb/README.md">LFB</a> (CVPR'2019)</td>
    <td></td>
  </tr>
  <tr>
    <td colspan="4" style="font-weight:bold;">Supported Datasets</td>
  </tr>
  <tr>
    <td> AVA(<a href="https://research.google.com/ava/index.html">Homepage</a>) (CVPR'2018)</td>
  </tr>
  <tr>
</table>


## SpatioTemporal Action Detection Webcam Demo

A demo script to implement real-time spatio-temporal action detection from a web camera is provided in demo\webcam_demo_spatiotemporal_det.py.

You can either run the script directly and use the default arguments, or manually change them to your liking.  

```shell
python demo/webcam_demo_spatiotemporal_det.py \
    [--config ${SPATIOTEMPORAL_ACTION_DETECTION_CONFIG_FILE}] \
    [--checkpoint ${SPATIOTEMPORAL_ACTION_DETECTION_CHECKPOINT}] \
    [--action-score-thr ${ACTION_DETECTION_SCORE_THRESHOLD}] \
    [--det-config ${HUMAN_DETECTION_CONFIG_FILE}] \
    [--det-checkpoint ${HUMAN_DETECTION_CHECKPOINT}] \
    [--det-score-thr ${HUMAN_DETECTION_SCORE_THRESHOLD}] \
    [--input-video] ${INPUT_VIDEO} \
    [--label-map ${LABEL_MAP}] \
    [--device ${DEVICE}] \
    [--output-fps ${OUTPUT_FPS}] \
    [--out-filename ${OUTPUT_FILENAME}] \
    [--show] \
    [--display-height] ${DISPLAY_HEIGHT} \
    [--display-width] ${DISPLAY_WIDTH} \
    [--predict-stepsize ${PREDICT_STEPSIZE}] \
    [--clip-vis-length] ${CLIP_VIS_LENGTH
```

Argument description:

- `SPATIOTEMPORAL_ACTION_DETECTION_CONFIG_FILE`: The spatiotemporal action detection config file path.
- `SPATIOTEMPORAL_ACTION_DETECTION_CHECKPOINT`: The spatiotemporal action detection checkpoint path or URL (You can find the URL by clicking in the ).
- `ACTION_DETECTION_SCORE_THRESHOLD`: The score threshold for action detection.
- `HUMAN_DETECTION_CONFIG_FILE`: The human detection config file path.
- `HUMAN_DETECTION_CHECKPOINT`: The human detection checkpoint URL.
- `HUMAN_DETECTION_SCORE_THRE`: The score threshold for human detection.
- `INPUT_VIDEO`: The webcam id or video path of the source.
- `LABEL_MAP`: The label map used.
- `DEVICE`: Type of device to run the demo. Allowed values are cuda device like `cuda:0` or `cpu`.
- `OUTPUT_FPS`: The FPS of demo video output.
- `OUTPUT_FILENAME`: Path to the output file which is a video format.
- `--show`: Whether to show predictions with `cv2.imshow`.
- `DISPLAY_HEIGHT`: The height of the display frame.
- `DISPLAY_WIDTH`: The width of the display frame.
- `PREDICT_STEPSIZE`: Make a prediction per N frames.
- `CLIP_VIS_LENGTH`: The number of the draw frames for each clip. In other words, for each clip, there are at most `CLIP_VIS_LENGTH` frames to be draw around the keyframe.

Example:

 Use the Faster RCNN as the human detector, SlowOnly-8x8-R101 as the action detector. Making predictions per 40 frames, and FPS of the output is 20. Show predictions with `cv2.imshow`.

```shell
python demo/webcam_demo_spatiotemporal_det.py \
    --input-video 0 \
    --config configs/detection/ava/slowonly_omnisource_pretrained_r101_8x8x1_20e_ava_rgb.py \
    --checkpoint https://download.openmmlab.com/mmaction/detection/ava/slowonly_omnisource_pretrained_r101_8x8x1_20e_ava_rgb/slowonly_omnisource_pretrained_r101_8x8x1_20e_ava_rgb_20201217-16378594.pth \
    --det-config demo/faster_rcnn_r50_fpn_2x_coco.py \
    --det-checkpoint http://download.openmmlab.com/mmdetection/v2.0/faster_rcnn/faster_rcnn_r50_fpn_2x_coco/faster_rcnn_r50_fpn_2x_coco_bbox_mAP-0.384_20200504_210434-a5d8aa15.pth \
    --det-score-thr 0.9 \
    --action-score-thr 0.5 \
    --label-map tools/data/ava/label_map.txt \
    --predict-stepsize 40 \
    --output-fps 20 \
    --show
```


# References
* [MMAction2](https://github.com/open-mmlab/mmaction2)

