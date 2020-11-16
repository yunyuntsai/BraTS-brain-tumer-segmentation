# Biomedical Image Anlysis Final: Brain Tumor Segmentaion

### **Motivation:**</br>
Quantitative assessment of brain tumor is an essential part of diagnose procedure. In this project, we aim to use object segmentation method to distinguish tumor part from Brain magnetic resonance images.

### **Our goal:**</br>
We demonstrate the effectiveness of a **3D-UNet** in the context of the **BraTS 2019 Challenge** and intend to improve the segmentation performance by using weighted mean square error (mse) loss function. 

### **Dataset**</br>
BraTS dataset is from Multimodal Brain Tumor Segmentation Challenge 2019. All BraTS multimodal scans are available as NIfTI files (.nii.gz). For each patient a T1 weighted (T1w), a post-contrast enhanced T1-weighted (T1CE), a T2-weighted (T2w) and a Fluid-Attenuated Inversion Recovery (FLAIR) MRI was provided. Data includes 210 glioblastoma (GBM/HGG) and 75 lower grade glioma (LGG) Pre-operative multimodal MRI scans. The MRI originate from 19 institutions and were acquired with diﬀerent protocols, magnetic ﬁeld strengths and MRI scanners. Annotations comprise the GD-enhancing tumor (ET), the peritumoral edema (ED), and the necrotic and non-enhancing tumor core (NCR/NET).

**Sample data of MRI slice: (Left: Original MRI, Right: Ground Truth)**</br></br>
<img src="https://user-images.githubusercontent.com/20013955/99252183-8c823800-2849-11eb-9be9-651845baaf7e.png" width="600" height="300" />


### **The Archtecture of 3D-UNet**</br>

As the following figure shows, our network architecture is a 3D-Unet. It consists of encoder part (left) and decoder part (right). The encoder part follows the typical architecture of convolutional neural network, including repeated application of two 3x3 convolutions (unpadded convolutions), each followed by a leaky rectiﬁed linear unit (lReLU) and a 2x2 max pooling operation with stride 2 for downsampling. Every step in the decoder part consists of an upsampling of the feature map followed by a 3*3 convolution (“up-convolution”).</br>

<img src="https://user-images.githubusercontent.com/20013955/99251436-52646680-2848-11eb-9841-1c02873e3f37.PNG" width="600" height="300" />

### **Evaluation**

We evaluate our model with two kinds of dataset. Both of them are extracted from **HGG testing set**. The first one uses **only FLAIR MRI** to train and the second combines **FLAIR and T1CE MRI**. </br>
As Table shows the testing results of our two model trained with different MRI data, we empirically discover that the result of model trained with FLAIR and T1CE data is better than model with only FLAIR data. As the Dice score of FLAIR and T1CE is higher than only FLAIR and Hausdorff distance is smaller as well.</br> 
<img src="https://user-images.githubusercontent.com/20013955/99253787-53979280-284c-11eb-9efd-63531b638079.PNG" width="400" height="200" />


