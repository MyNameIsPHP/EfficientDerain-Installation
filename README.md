# Installation of EfficientDerain
This is the installation, training and validating guide for EfficientDerain network in the paper "EfficientDeRain: Learning Pixel-wise Dilation Filtering for High-Efficiency Single-Image Deraining
" (https://arxiv.org/abs/2009.09238)


## Installation
Run the script below to install (Conda):
```
conda create -n proposed1 python=3.6.7
conda activate proposed1
conda install -y pytorch=1.4.0 cudatoolkit=10.0 torchvision -c pytorch
conda install h5py opencv
pip install tensorboardX scikit-image==0.17.2 pytorch-msssim==0.2.1
```

## Datasets
To train and evaluate the models, please download training and testing datasets from 
https://drive.google.com/file/d/1IBENJqN6XU5HMlSQ2W7jkdW22Z1x4W9K/view?usp=sharing
and place the unzipped folders into the project folder.

## Pretrained models
Here is the urls of pretrained models (includes v3_rain100H, v3_rain1400, v3_SPA, v4_rain100H, v4_rain1400, v4_SPA) : 

direct download: 
http://www.xujuefei.com/models_effderain.zip

google drive:
https://drive.google.com/file/d/1OBAIG4su6vIPEimTX7PNuQTxZDjtCUD8/view?usp=sharing

baiduyun:
https://pan.baidu.com/s/1kFWP-b3tD8Ms7VCBj9f1kw (pwd: vr3g)

## Train
- The code shown corresponds to version **v3**, for **v4** change the value of argument "**rainaug**" in file "**./train_*.sh**" to the "**true**" (train_*.sh means it's the training script of dataset *) 
- Unzip the "Streaks_Garg06.zip" in the "./rainmix"
- Change the value of argument "**baseroot**" in file "**./train.sh**" to **the path of training data** (Crop size must be divisible by 16)
- Edit the function "**get_files**" in file "**./utils**" according to the format of the training data
- Execute
```
sh train___.sh
```

## Test

- The code shown corresponds to version **v3**
- Change the value of argument "**load_name**" in file "**./test.sh**" to **the path of pretained model**
- Change the value of argument "**baseroot**" in file "**./test.sh**" to **the path of testing data**
- Edit the function "**get_files**" in file "**./utils**" according to the format of the testing data
- Execute

```
sh test.sh
```


## Bibtex

```
@inproceedings{guo2020efficientderain,
      title={EfficientDeRain: Learning Pixel-wise Dilation Filtering for High-Efficiency Single-Image Deraining}, 
      author={Qing Guo and Jingyang Sun and Felix Juefei-Xu and Lei Ma and Xiaofei Xie and Wei Feng and Yang Liu},
      year={2021},
      booktitle={AAAI}
}
```

