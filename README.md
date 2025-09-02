# BioSR Dataset (biosr_dataset)

## Overview

This DeepTrackAI repository provides a preprocessed part of the **BioSR** dataset, available from [figshare (DOI: 10.6084/m9.figshare.13264793.v9)](https://doi.org/10.6084/m9.figshare.13264793.v9) and originally published by [Chang Qiao et al.,  Nature Methods, 2021](https://doi.org/10.1038/s41592-020-01048-5). 

The original dataset consists of paired low-resolution (LR) and high-resolution (HR) fluorescence microscopy images for training and benchmarking super-resolution reconstruction methods, covering four biology structures (Clatrin Coated Pits, Endoplasmatic Reticulum, Microtubules, F-actin), nine signal levels (15-600 average photon count), and two upscaling-factors (linear SIM and non-linear SIM).

This repo only includes the Microtubules folder and the images in this repository have been cropped into 128 × 128 pixel patches, saved as 32-bit grayscale TIFF files, and organized into training/validate/test splits to be directly usable in deep learning workflows, while preserving the original content and licensing terms.

### Summary
- **Number of images**:  
  - Training: 41,040 pairs
  - Validation: 2,160 pairs  
  - Test: 150 HR images × 9 LR signal levels (1,350 LR images total). Each subfolder corresponds to a different signal-to-noise level, reflecting increasing average photon counts (15–600 photons).
- **Image size**: 128 × 128 pixels  
- **Image format**: 32-bit grayscale TIFF 

---

## Original Source

- **Title**: BioSR: a biological image dataset for super-resolution microscopy  
- **Authors**: Chang Qiao and Di Li
- **Source**: [figshare (DOI: 10.6084/m9.figshare.13264793.v9)](https://doi.org/10.6084/m9.figshare.13264793.v9)  
- **Reference**: Qiao C, Li Y, Qu J, et al. *Nature Methods* 18: 194–202 (2021). [DOI: 10.1038/s41592-020-01048-5](https://doi.org/10.1038/s41592-020-01048-5)  
- **License**: [Creative Commons Attribution 4.0 International (CC BY 4.0)](https://creativecommons.org/licenses/by/4.0/)

If you use this dataset in your research, please follow the licensing requirements and properly attribute the original authors.

---

## Dataset Structure

```bash
/biosr_dataset
└── BioSR/
    └── Microtubules/
        ├── training_wf/      # Low-resolution training images
        │   ├── 00000001.tif
        │   ├── 00000002.tif
        │   └── ...
        ├── training_gt/      # High-resolution training images
        │   ├── 00000001.tif
        │   ├── 00000002.tif
        │   └── ...
        ├── validate_wf/      # Low-resolution validation images
        │   ├── 00000001.tif
        │   ├── 00000002.tif
        │   └── ...
        ├── validate_gt/      # High-resolution validation images
        │   ├── 00000001.tif
        │   ├── 00000002.tif
        │   └── ...
        ├── test_wf/          # Low-resolution test images, 9 signal levels
        │   ├── level_01/     # Lowest photon count (~15), lowest SNR
        │   │   ├── 001.tif
        │   │   ├── 002.tif
        │   │   └── ...
        │   ├── level_02/
        │   │   ├── 001.tif
        │   │   ├── 002.tif
        │   │   └── ...
        │   ├── ...
        │   └── level_09/     # Highest photon count (~600), highest SNR
        └── test_gt/          # High-resolution test images
            ├── 001.tif
            ├── 002.tif
            └── ...
```

Each filename is a sequential numerical identifier. In the test set, subfolders correspond to different signal levels (photon counts), with level_01 being the noisiest and level_09 the cleanest.

---

## How to Access the Data

### Clone the Repository
```bash
git clone https://github.com/DeepTrackAI/biosr_dataset
cd biosr_dataset
```

---

## Attribution

This replication dataset is based on the original BIOSR dataset. When using this replication, please cite both the dataset and the original paper.

### Cite the dataset:

Qiao, Chang; Li, Di. *BioSR: a biological image dataset for super-resolution microscopy.* (2020)
[https://doi.org/10.6084/m9.figshare.13264793.v9](https://doi.org/10.6084/m9.figshare.13264793.v9)

```bibtex
@article{Qiao2020,
author = "Chang Qiao and Di Li",
title = "{BioSR: a biological image dataset for super-resolution microscopy}",
year = "2020",
month = "11",
url = "https://figshare.com/articles/dataset/BioSR/13264793",
doi = "10.6084/m9.figshare.13264793.v9"
}
```

### Cite the original paper:
Qiao C, Li Y, Qu J, et al. *Evaluation and development of deep neural networks for image super-resolution in optical microscopy.* Nature Methods, 18: 194–202 (2021).  
[https://doi.org/10.1038/s41592-020-01048-5](https://doi.org/10.1038/s41592-020-01048-5)

```bibtex
@article{qiao2021biosr,
  title={Evaluation and development of deep neural networks for image super-resolution in optical microscopy},
  author={Qiao, Chang and Li, Yuxiang and Qu, Junle and others},
  journal={Nature Methods},
  volume={18},
  pages={194--202},
  year={2021},
  publisher={Nature Publishing Group},
  doi={10.1038/s41592-020-01048-5}
}
```

---

## License

This dataset is shared under the **Creative Commons Attribution 4.0 International (CC BY 4.0)** License, following the original licensing terms.

