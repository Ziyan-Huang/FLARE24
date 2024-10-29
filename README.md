# 🔍 A 5.6M Parameter U-Net for Efficient Whole-body Tumor Segmentation (For MICCAI FLARE2024 challenge Task1)

## 🆚 Key Differences Between Our Method and nnUNetV2

| Configuration | Our Method 🚀 | nnUNetV2 🗿 |
|---------------|--------------|-------------|
| Number of Stages ⬇️ | 4 | 6 |
| Training Epochs ⏱️ | 2000 | 1000 |
| Learning Rate 📊 | 0.001 | 0.01 |
| Target Spacing 📐 | 2, 2, 3 | 0.8, 0.8, 3 |

> 💡 Our method achieves efficient segmentation with fewer stages and lower resample resolution.

## 📂 Key Files in this Repository

Only two files you need to focus on:

1. [nnUNetTrainer_varianst.py](./nnunetv2/training/nnUNetTrainer/nnUNetTrainer_varianst.py)
   - Custom nnUNet trainer with modified training parameters
   
2. [plans.json](./nnUNet_results/Dataset024_FLARE24_Task1/nnUNetTrainer_Epoch2000_Lr1e3__nnUNetPlans__3d_fullres_S4D2W32/plans.json) 
   - Network architecture and configuration settings

## 📊 Data

- **Dataset**: FLARE24 Task1
- **Data Usage**: 5000 partial labeled data (treated as fully labeled without any special handling for partial labels)
- **Preprocessing**: Default nnUNet procedure without any modification

## 📊 Quantitative Results

| Methods | Public Validation |  | Online Validation |  | Testing |  |
|---------|------------------|--|------------------|--|---------|--|
|         | DSC(%) | NSD(%) | DSC(%) | NSD(%) | DSC(%) | NSD(%) |
| Ours    | 25.34 ± 31.56 | 24.40 ± 27.80 | - | - | - | - |

## 🖼️ Visualization

<img src="imgs/flare23-results.png" width="600"/>

*Two examples with good segmentation results and two examples with bad segmentation results in the validation set.*