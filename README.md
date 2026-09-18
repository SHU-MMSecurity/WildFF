# WildFF

WildFF is an **in-the-wild face forensics dataset** used in the paper  
**WildDFDet: Unsupervised and Noise-Robust DeepFake Detection in the Wild**.

<img width="864" height="418" alt="examples" src="https://github.com/user-attachments/assets/10a2c5bc-8163-4ac3-907e-8c0775e4a8b2" />

## Dataset Overview

- Collected from real-world online videos (e.g., Bilibili, TikTok, YouTube, X).
- WildFF-V1/V2/V3 contain **unlabeled**, **clean-labeled**, and **noisy-labeled** samples for evaluating unsupervised and supervised DeepFake detectors.
- All WildFF-V1/V2/V3 versions share the same clean test set.
- An additional auxiliary subset, **WildFF-PLG-1K**, contains **1,000 unlabeled wild face images** independently collected for training the pseudo-label generator (PLG) in WildDFDet.
- WildFF-PLG-1K is separate from the WildFF-V1/V2/V3 benchmark splits and is not used as the WildFF evaluation set.

## Dataset Splits

| Version   | Unlabeled | Clean Labeled | Noisy Labeled | Test (Clean) |
|-----------|----------:|--------------:|--------------:|-------------:|
| WildFF-V1 | 5000      | 3500          | 1500          | 2000         |
| WildFF-V2 | 5000      | 600           | 400           | 2000         |
| WildFF-V3 | 1000      | 50            | 50            | 2000         |

- Unsupervised methods may use all training samples.
- Supervised methods are trained only on labeled samples.
- All versions share the same clean test set.

> **Note:** The 1,000 unlabeled wild face images used to train the PLG module in WildDFDet are provided separately as **WildFF-PLG-1K**. They are **not** the 1,000 unlabeled samples listed in WildFF-V3 and are not included in the WildFF-V1/V2/V3 training or test splits.

## WildFF-PLG-1K: Auxiliary Unlabeled Data for PLG

In the WildDFDet paper, we use **1,000 unlabeled wild face images collected from the Internet** to construct the pseudo-label generator (PLG). To make this experimental setting explicit and reproducible, these samples are separately provided as **WildFF-PLG-1K**.

WildFF-PLG-1K contains **1,000 unlabeled in-the-wild face images** independently collected from real-world online videos. This subset is used **only for training the PLG module to construct the pseudo-label generator** in WildDFDet. No ground-truth real/fake labels from these images are used during PLG training.

WildFF-PLG-1K is an **auxiliary unlabeled training subset** and is separate from the WildFF-V1/V2/V3 benchmark splits. Specifically:

- Number of images: **1,000**
- Ground-truth labels used during PLG training: **None**
- Purpose: **training the PLG module / constructing the pseudo-label generator**
- Part of WildFF-V1/V2/V3 training splits: **No**
- Part of the shared WildFF clean test set: **No**
- Used for WildFF evaluation: **No**

The 1,000 unlabeled images used for PLG training are provided separately in the **WildFF-PLG-1K** folder.

## Construction Pipeline

<img width="1054" height="175" alt="image" src="https://github.com/user-attachments/assets/aa5ff6d8-9075-47f8-9d03-42c9d0fd81db" />

First, we collect a large volume of videos from popular online video-sharing platforms, including Bilibili, TikTok, Red Book, X, YouTube, and Instagram. Then, we filter these videos using a diverse set of common face-related search tags (e.g., interview, live stream, face swap, synthetic faces) to select real and fake videos that contain faces.

Next, the collected videos are decoded at a rate of one Frame Per Second (FPS) to obtain a representative set of frames. We then employ advanced face detection models (RetinaFace and MTCNN) to identify and crop the largest face in each frame. Faces with a detection confidence below 0.9 or a resolution lower than 64×64 pixels are discarded to ensure basic quality. This process produces a large number of unlabeled face image samples.

The **WildFF-PLG-1K** subset follows the same general collection and preprocessing pipeline. A separate set of 1,000 unlabeled face images is selected for training the PLG module. These images are maintained separately from the WildFF-V1/V2/V3 benchmark splits and are used exclusively for pseudo-label generator construction.

For the WildFF-V1/V2/V3 benchmark splits, we randomly select part of the collected face images for labeling. The labeled samples are divided into two parts. Clean labels come from videos with watermark markings, i.e., videos identified as AI-generated fake by online platforms, as well as faces we manually label as fake and real. Noisy-label samples are derived from human annotation errors, where labels are randomly flipped with a certain probability, as well as simulated label-flipping attacks, where labels for a subset are flipped. The final benchmark dataset therefore contains a mixture of labeled and unlabeled data.

## Dataset Distribution

<img width="1130" height="370" alt="image" src="https://github.com/user-attachments/assets/40f096fb-28c9-4786-b6a0-c025ca3d2e87" />

Our dataset maintains a balanced gender ratio, diverse age groups, and a wide range of skin tones. These statistics confirm that WildFF covers a diverse range of themes, enhancing its validity as a real-world benchmark.

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

