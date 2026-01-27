# WildFF

WildFF is an **in-the-wild face forgery (DeepFake) dataset** used in the paper  
**WildDFDet: Unsupervised and Noise-Robust DeepFake Detection in the Wild**.

<img width="864" height="418" alt="examples" src="https://github.com/user-attachments/assets/10a2c5bc-8163-4ac3-907e-8c0775e4a8b2" />

## Dataset Overview

- Collected from real-world online videos (e.g., Bilibili, TikTok, YouTube, X).
- Contains **unlabeled**, **clean-labeled**, and **noisy-labeled** samples.
- Designed for evaluating **unsupervised** and **supervised** DeepFake detectors.

## Dataset Splits

| Version   | Unlabeled | Clean Labeled | Noisy Labeled | Test (Clean) |
|-----------|----------:|--------------:|--------------:|-------------:|
| WildFF-V1 | 5000      | 3500          | 1500          | 2000         |
| WildFF-V2 | 5000      | 600           | 400           | 2000         |
| WildFF-V3 | 1000      | 50            | 50            | 2000         |

- Unsupervised methods may use all training samples.
- Supervised methods are trained only on labeled samples.
- All versions share the same clean test set.

## Construction Pipeline

<img width="1054" height="175" alt="image" src="https://github.com/user-attachments/assets/aa5ff6d8-9075-47f8-9d03-42c9d0fd81db" />


## Dataset Distribution

<img width="1130" height="370" alt="image" src="https://github.com/user-attachments/assets/40f096fb-28c9-4786-b6a0-c025ca3d2e87" />


## Download

Baidu Netdisk link: https://pan.baidu.com/s/16vdUrahUrbXBO2ErxWlvgQ?pwd=89af
Password: 89af


## Usage & License

- The dataset is released **for academic research only**.
- Please follow the terms of service of the original video platforms.
- If you use WildFF, please cite **WildDFDet**.

## Contact

Shichuang Xie  
shichuang_xie@shu.edu.cn

