# Spatiotemporal Action Detection

### Introduction
Detect human actions both in spatial and temporal dimensions using MMAction2.

MMAction2 is an open-source toolbox for video understanding based on PyTorch.
It is a part of the [OpenMMLab](https://openmmlab.com/) project.

### Installation

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

### Supported Methods

<table style="margin-left:auto;margin-right:auto;font-size:1.3vw;padding:3px 5px;text-align:center;vertical-align:center;">
  <tr>
    <td colspan="5" style="font-weight:bold;">Spatio-Temporal Action Detection</td>
  </tr>
  <tr>
    <td><a href="https://github.com/mkatras11/Action_Detection_mmaction2/tree/main/configs/detection/acrn/README.md">ACRN</a> (ECCV'2018)</td>
    <td><a href="https://github.com/mkatras11/Action_Detection_mmaction2/tree/main/configs/detection/ava/README.md">SlowOnly+Fast R-CNN</a> (ICCV'2019)</td>
    <td><a href="https:https://github.com/mkatras11/Action_Detection_mmaction2/tree/main/configs/detection/ava/README.md">SlowFast+Fast R-CNN</a> (ICCV'2019)</td>
    <td><a href="https://github.com/mkatras11/Action_Detection_mmaction2/tree/main/configs/detection/lfb/README.md">LFB</a> (CVPR'2019)</td>
    <td></td>
  </tr>
  <tr>
</table>

### Supported Datasets

<table style="margin-left:auto;margin-right:auto;font-size:1.3vw;padding:3px 5px;text-align:center;vertical-align:center;">
  <tr>
    <td colspan="4" style="font-weight:bold;">Spatio-Temporal Action Detection</td>
  </tr>
  <tr>
    <td><a href="https://github.com/open-mmlab/mmaction2/blob/master/tools/data/ucf101_24/README.md">UCF101-24</a> (<a href="http://www.thumos.info/download.html">Homepage</a>) (CRCV-IR-12-01)</td>
    <td><a href="https://github.com/open-mmlab/mmaction2/blob/master/tools/data/jhmdb/README.md">JHMDB</a> (<a href="http://jhmdb.is.tue.mpg.de/">Homepage</a>) (ICCV'2015)</td>
    <td><a href="https://github.com/open-mmlab/mmaction2/blob/master/tools/data/ava/README.md">AVA</a> (<a href="https://research.google.com/ava/index.html">Homepage</a>) (CVPR'2018)</td>
    <td></td>
  </tr>
  <tr>
</table>

### References
* [MMAction2](https://github.com/open-mmlab/mmaction2)

