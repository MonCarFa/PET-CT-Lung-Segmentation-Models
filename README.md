# PET-CT-Lung-Segmentation-Models
Two open-source nnU-Net models for automatic segmentation of lung tumors on PET and CT images with and without respiratory motion compensation. In this repository the model weights are stored for the trained nnU-Net models as described in [Carles, M. et al. (2023)](#carles).

## Repository structure
This package contains 2 folders:
1. [PETModel](PETModel/): Model for lung tumor segmentation on PET.
2. [CTModel](CTModel/): Model for lung tumor segmentation on CT.

## Installation
1. For this project the nnU-Net v1 was utilized as described in [Isensee, F. et al. (2021)](#isensee). Clone the nnU-Net repository and follow the [installation instructions](https://github.com/MIC-DKFZ/nnUNet/tree/nnunetv1).

2. Clone this repository into a seperate directory to download both, the PET and the CT model weights
```bash
git clone https://github.com/MonCarFa/PET-CT-Lung-Segmentation-Models.git
```
3. Copy the Task directory of the desired model into the nnU-Net directory at the correct location. For example:
```bash
your/path/to/nnUNet_trained_models/nnUNet/3d_fullres/Task998_LungCTSegmentation

your/path/to/nnUNet_trained_models/nnUNet/3d_fullres/Task999_LungPETSegmentation
```
If the directories do not exist create them and make sure you've set up the [environment variables](https://github.com/MIC-DKFZ/nnUNet/blob/nnunetv1/documentation/setting_up_paths.md) correctly.

## Prediction

For lung tumors segmentation on CT images execute the following script
```bash
nnUNet_predict -i FOLDER_WITH_TEST_CASES -o OUTPUT_FOLDER -tr nnUNetTrainerV2 -ctr nnUNetTrainerV2CascadeFullRes -m 3d_fullres -p nnUNetPlansv2.1 -t Task998_LungCTSegmentation
```
and for segmentation on PET images execute
```bash
nnUNet_predict -i FOLDER_WITH_TEST_CASES -o OUTPUT_FOLDER -tr nnUNetTrainerV2 -ctr nnUNetTrainerV2CascadeFullRes -m 3d_fullres -p nnUNetPlansv2.1 -t Task999_LungPETSegmentation
```
Substitute `FOLDER_WITH_TEST_CASES` and `OUTPUT_FOLDER` with directory paths of your choice.

## References
1. <a id="carles"></a>Carles, M. et al. (2023). Development and evaluation of two open-source nnU-Net models for automatic segmentation of lung tumors on PET and CT images with and without respiratory motion compensation. European Radiology, XX(XX), XXXX-XXXX.doi:10.XXXX/XXXX...
2. <a id="isensee"></a>Isensee, F. et al. (2021). nnU-Net: a self-configuring method for deep learning-based biomedical image segmentation. Nature methods, 18(2), 203–211. https://doi.org/10.1038/s41592-020-01008-z

## Author
Montserrat Carles Fariña  <montserrat_carles@iislafe.es>

THANK YOU FOR YOUR INTEREST IN THIS PACKAGE 

If you have any questions, comments or suggestions about this package, please do not hesitate to contact me!

## History
- Version 1.0: March 2023

## Citation
Please cite the following paper if you use this work for your research:

```
Carles, M. et al. (2023). Development and evaluation of two open-source nnU-Net models for automatic segmentation of lung tumors on PET and CT images with and without respiratory motion compensation. European Radiology, XX(XX), XXXX-XXXX.doi:10.XXXX/XXXX...
```