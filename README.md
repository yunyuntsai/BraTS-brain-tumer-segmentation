# Biomedical Image Anlysis Final: Brain Tumor Segmentaion

**Motivation:**</br>
Quantitative assessment of brain tumor is an essential part of diagnose procedure. In this project, we aim to use object segmentation method to distinguish tumor part from Brain magnetic resonance images.

**Our goal:**</br>
We demonstrate the effectiveness of a **3D-UNet** in the context of the **BraTS 2019 Challenge** and intend to improve the segmentation performance by using weighted mean square error (mse) loss function. 

**Dataset**</br>
BraTS dataset is from Multimodal Brain Tumor Segmentation Challenge 2019. All BraTS multimodal scans are available as NIfTI files (.nii.gz). For each patient a T1 weighted (T1w), a post-contrast enhanced T1-weighted (T1CE), a T2-weighted (T2w) and a Fluid-Attenuated Inversion Recovery (FLAIR) MRI was provided. Data includes 210 glioblastoma (GBM/HGG) and 75 lower grade glioma (LGG) Pre-operative multimodal MRI scans. The MRI originate from 19 institutions and were acquired with diﬀerent protocols, magnetic ﬁeld strengths and MRI scanners. Annotations comprise the GD-enhancing tumor (ET), the peritumoral edema (ED), and the necrotic and non-enhancing tumor core (NCR/NET).

**Sample data of MRI slice: (Left: Original MRI, Right: Ground Truth)**</br></br>
<img src="https://user-images.githubusercontent.com/20013955/99252183-8c823800-2849-11eb-9be9-651845baaf7e.png" width="400" height="200" />


**The Archtecture of 3D-UNet**
![Alt text](https://user-images.githubusercontent.com/20013955/99251436-52646680-2848-11eb-9841-1c02873e3f37.PNG)
