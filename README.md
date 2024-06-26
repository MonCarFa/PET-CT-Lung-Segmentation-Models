# PET-CT-Lung-Segmentation-Models
Two open-source nnU-Net models for automatic segmentation of lung tumors on PET and CT images with and without respiratory motion compensation. In this repository the model weights are stored for the trained nnU-Net models as described in [Carles, M. et al. (2024)](#carles).

## Installation
1. For this project the nnU-Net v1 was utilized as described in [Isensee, F. et al. (2021)](#isensee). Clone the nnU-Net repository and follow the [installation instructions](https://github.com/MIC-DKFZ/nnUNet/tree/nnunetv1).

2. Download and extract the [CT model](https://www.kaggle.com/models/dejankuhn/ct-lung-tumor-segmentation-model) or the [PET model](https://www.kaggle.com/models/dejankuhn/pet-lung-tumor-segmentation-model).
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
1. <a id="carles"></a> Carles, M., Kuhn, D., Fechter, T. et al. Development and evaluation of two open-source nnU-Net models for automatic segmentation of lung tumors on PET and CT images with and without respiratory motion compensation. Eur Radiol (2024). https://doi.org/10.1007/s00330-024-10751-2
2. <a id="isensee"></a>Isensee, F. et al. (2021). nnU-Net: a self-configuring method for deep learning-based biomedical image segmentation. Nature methods, 18(2), 203–211. https://doi.org/10.1038/s41592-020-01008-z

## Author
Montserrat Carles Fariña  <montserrat_carles@iislafe.es>

THANK YOU FOR YOUR INTEREST IN THIS PACKAGE 

If you have any questions, comments or suggestions about this package, please do not hesitate to contact me!

## History
- Version 1.0: April 2024

## Citation
Please cite the following paper if you use this work for your research:

```
Carles, M., Kuhn, D., Fechter, T. et al. Development and evaluation of two open-source nnU-Net models for automatic segmentation of lung tumors on PET and CT images with and without respiratory motion compensation. Eur Radiol (2024). https://doi.org/10.1007/s00330-024-10751-2
```
