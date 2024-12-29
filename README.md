# [Colorization-inspired Customized Low-Light Image Enhancement by A Decoupled Network](https://ieeexplore.ieee.org/document/10815605)
## Introduction

This is the official implementation of "Colorization-inspired Customized Low-Light Image Enhancement by A Decoupled Network" published in TNNLS![pipeline](image-20231213222110349](https://github.com/wangchx67/CCNet/blob/main/figs\pipeline.png)

Recently, numerous inspirational approaches have been proposed to enhance the visual quality of the images captured under poor lighting conditions. Simultaneously, in order to accommodate diverse user aesthetics, researchers have explored customized operations within the enhancement process. However, most existing researches ignore the significance of the chrominance component, which often leads to unsatisfactory results in terms of color. To address this issue, we novelly decompose the Low-Light Image Enhancement (LLIE) task into the brightening and colorization sub-tasks, and develop a decoupled network called CCNet for Colorization-inspired Customized enhancement. Specifically, the brightening sub-task aims to restore images with normal contrast, less noise, and sharper details. While the colorization sub-task utilizes the chrominance information from low-light images as color guidance to predict rich chrominance in enhanced images. Then, in the inference stage, users can adjust the color style or the saturation of color guidance to obtain customized results. Extensive experiments demonstrate that our proposed method achieves superior performance in both general and customized LLIE tasks—particularly in terms of improving chrominance components.  

![image-20231213222110349](https://github.com/wangchx67/CCNet/blob/main/figs/exp)

## Installation

```
conda create --name CCNet --file requirements.txt
conda activate CCNet
```

## Datasets

- LSRW-Huawei and LSRW-Nikon can be found in [here](https://github.com/JianghaiSCU/R2RNet).

## Run LLIE

For network training, you can modify the dataset path in `./options/train/LSRW_Huawei_lightness.yml` and `./options/train/LSRW_Huawei_lightness.yml`, and run the `sh run.sh`. **Remember delete the experiments folder for each training.**

For evaluation, you can modify the dataset path and model path in `./options/test/LSRW_Huawei.yml`. We have placed the pre-trained models in `./pre-trained` folder.

## Run customization

For convenient running customization process, we build a very simple UI. You can run the `./ui/main.py`. The simple guideline can be seen following figure.

![image-20231213231337708](https://github.com/wangchx67/BCNet/blob/main/figs/ui.png)

## Citation Information

If you find the project useful, please cite:

```
@ARTICLE{10815605,
  author={Jin, Zhi and Wang, Chenxi and Luo, Xing},
  journal={IEEE Transactions on Neural Networks and Learning Systems}, 
  title={Colorization-Inspired Customized Low-Light Image Enhancement by a Decoupled Network}, 
  year={2024},
  volume={},
  number={},
  pages={1-14},
  keywords={Image color analysis;Image enhancement;Histograms;Training;Feature extraction;Colored noise;Semantics;Object recognition;Lighting;Learning systems;Color transfer;customized enhancement;Fourier transform;low-light image enhancement (LLIE);user-guided image colorization},
  doi={10.1109/TNNLS.2024.3502424}}
  
@inproceedings{conf/mm/WangJ23,
	title = {Brighten-and-Colorize: A Decoupled Network for Customized Low-Light Image Enhancement.},
	year = {2023},
	booktitle = {ACM Multimedia},
	author = {{Chenxi Wang} and {Zhi Jin}},
	publisher = {ACM},
	booktitle = {Proceedings of the 31st ACM International Conference on Multimedia, MM 2023, Ottawa, ON, Canada, 29 October 2023- 3 November 2023}
}
```
