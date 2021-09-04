<div align="center">
	
# Detecting COVID-19 with Pneumonia    
</div>

In this paper, we propose a rapidly testing method which has a high productivity in a short time. In details, we will apply deep learning neural networks, e.g. ResNet50 and VGG19 to solve this problem. After that, we will proceed analysing pros and cons  of  those  models  for  a  thorough  vision  about  applying  artificial  intelligence  in  COVID-19  rapid  testing.

### Contents
1. [Introduction](#1-introduction)
2. [Prerequisites ](#2-prerequisites)
3. [Install](#3-install)
4. [Results](#4-results) 
5. [References](#5-references)
### 1. Introduction
#### Dataset's description
In this research, we use COVIDx dataset - which is a widely used dataset in recent research about COVID-19 nowadays.   
COVIDx Datset is a dataset synthesized from many a different source, which are in details: Cohen et al. [3], Chung [4], Chung [5], Radiological Society of North America [5],and Radiological Society of North America [6]. Additionally, this dataset also provides an image extension transfer tool: from `.mri` into `.jpg`. And the author moreover provide a code to support data pre-processing and getting rid of unnecessary part for synthesized data.
#### Method
We proposed using *diagnostic imaging*, which is an approach using Chest X-ray (CXR) image. This is due to its lower cost and faster testing time in comparison with RT PCR or CT Image.

#### Model approach
Throughout this research, we use 2 different approaches which are **ResNet50** and **VGG19** to solve this problem. VGG19 is a deep neural network architecture under-using residual design principals, it is also a compact architecture which has a low diversity of architectures. On the other hand, ResNet50 is a deep neural network harnessing residual design principles and it has a moderate diversity of architectures. This network brings many a high productivity in a large number of researching in classifying X-ray images. Despite each approach has its own benefits and drawbacks, both are proved their productivity through real application.

### 2. Prerequisites 
- Python >=  3.6
- Sklear >= 0.24.2
- NumPy >= 1.13.3
- Tensorflow >= 2.6
### 3. Install 
```bash
conda create -n covid-detect python==3.8 -y
conda activate covid-detect 
pip3 install -r requirements.txt
jupyter notebook
```
### 4. Results
#### Comparison between precision and number of parameters among models
| Architecture | Number of parameters (M) | Accuracy | Resolution |
|:---:|:---:|:--:|:--:|
| VGG19 | 29.76 trainable + 20.25 non-trainable | 86% | 480 x 480 |
| ResNet50 (14 epochs) | 25.93 trainable + 23.77 non-trainable | 77% |224 x 224 |
| ResNet50 (50 epochs) | 25.93 trainable + 23.77 non-trainable | 84% | 224 x 224 |

#### Comparison among models based on sensitivity
| Architecture | Non-respiratory disease | Pneumonia | COVID-19 |
|:---:|:---:|:--:|:--:|
| VGG19 | 96\% | 86\% | 82\% |
| ResNet50 (14 epochs) |  96\% | 85\% | 67\% |
| ResNet50 (50 epochs) | 86\% | 90\% | 80\% |

#### Comparison among models based on PPV
| Architecture | Non-respiratory disease | Pneumonia | COVID-19 |
|:---:|:---:|:--:|:--:|
| VGG19 |70\% | 80\%| 99\% |
| ResNet50 (14 epochs) |  56\% | 74\% | 97\% |
| ResNet50 (50 epochs) | 73\% | 71\% | 96\% |

## References 
- [1] Cleverley, J.; Piper, J.; Jones, M.M. The role of chest radiography in confirming covid-19 pneumonia. BMJ 2020, 370. 
- [2] Wang, L., Lin, Z.Q. & Wong, A. COVID-Net: a tailored deep convolutional neural network design for detection of COVID-19 cases from chest X-ray images. Sci Rep 10, 19549 (2020). https://doi.org/10.1038/s41598-020-76550-z
- [3] Cohen, J. P., Morrison, P., & Dao, L. COVID-19 image data collection. arXiv:2003.11597(2020)
- [4] Chung, A. Figure 1 COVID-19 chest x-ray data initiative. https://github.com/agchung/Figure1-COVID-chestxray-dataset (2020)
- [5] Chung, A. Actualmed COVID-19 chest x-ray data initiative. https://github.com/agchung/Actualmed-COVID-chestxray-dataset (2020)
- [6] Radiological Society of North America. COVID-19 radiography database. https://www.kaggle.com/tawsifurrahman/covid19-radiography-database (2019)
- [7] Radiological Society of North America. RSNA pneumonia detection challenge. https://www.kaggle.com/c/rsna-pneumonia-detection-challenge/data (2019).
- [8] Krizhevsky, A., Sutskever, I. & Hinton, G. E. (2012). ImageNet Classification with Deep Convolutional Neural Networks. In F. Pereira, C. J. C. Burges, L. Bottou & K. Q. Weinberger (ed.), Advances in Neural Information Processing Systems 25 (pp. 1097--1105) . Curran Associates, Inc. . 
- [9] K. Simonyan et al., Very deep convolutional networks for large-scale image recognition, 2015.
