# MonocularPureVisualSLAMComparison
# A Comparison of Monocular Visual SLAM and Visual Odometry Methods Applied to 3D Reconstruction
Over the past 30 years, there has been extensive research on the complex and unsolved problem of monocular pure visual 3D reconstruction. The objective of monocular 3D reconstruction is to generate 3D representations of an environment using only a sequence of images as input. Previous studies have explored various hardware options such as radars, lasers, GPS, INS, cameras, and combinations to tackle this problem. Camera-based approaches have investigated the combination of infrared sensors with RGB-D input or using camera arrays to capture simultaneously sets of images from different angles for triangulation. Another approach involves using uniquely monocular RGB sensors to capture frames from multiple viewpoints. This method, known as monocular RGB or monocular pure visual input, has attracted attention due to its affordability and the widespread availability of sensors in handheld devices like smartphones, tablets, and laptops. Monocular Simultaneous Landing and Mapping (SLAM), Visual Odometry (VO), and Structure from Motion (SFM) are three techniques that leverage monocular input to reconstruct 3D environments and estimate motion. These systems have shown promising results indoors and outdoors, eliminating the limitations of range-bound sensors such as lasers or radars.

SLAM, VO, and SFM are disciplines used to achieve 3D reconstruction. SLAM, originating from robotics, focuses on estimating the environment map to calculate the trajectory of a robot, enabling autonomous navigation in various applications. In computer vision, SFM aims to recover the environment's geometry, while VO concentrates on calculating the trajectory and orientation of a moving camera. However, it has been observed that the best results are obtained when both problems are simultaneously solved and optimized. Therefore, it is common to find VO methods incorporating SFM modules to enhance performance and SFM methods utilizing VO for improved estimation or optimization tasks. In this study, we aimed to identify the most effective monocular RGB methods for 3D reconstruction by considering approaches from all three disciplines.

As an ill-posed problem, monocular RGB 3D reconstruction has been approached from various perspectives, combining different techniques. An early classification categorized methods as feature- or appearance-based, but it failed to encompass all the state-of-the-art SLAM, VO, and SFM techniques. A more comprehensive taxonomy based on the study of (Engel, Koltun, & Cremers, 2017) was described in [see taxonomy](https://github.com/erickherreraresearch/TaxonomyPureVisualMonocularSLAM) provides a better framework, considering three classifications: dense, sparse, direct, indirect, classic, and machine learning-based approaches. This taxonomy offers a more thorough classification of monocular RGB 3D reconstruction systems. In the same work, the authors listed 42 methods classified according to this extended taxonomy. However, upon careful analysis, it was found that many of these methods were inadequately evaluated on large datasets or under different motion patterns and lighting conditions. Moreover, some studies did not test the methods for indoor and outdoor environments, and the reported results were not always obtained using the same metrics, making it challenging to compare and select the most suitable methods. Additionally, most studies compared their results to existing state-of-the-art methods, presenting average mean or median values without providing inferential statistical analysis, making the reported differences or improvements insignificant.

This is the official repository for the article: "Comparison of Monocular Visual SLAM and Visual Odometry Methods Applied to 3D Reconstruction", where we provide the full database that was gathered after more than 10000 executions of ten monocular pure visual SLAM, VO, or SFM methods that were selected based on the extended taxonomy described in [see taxonomy](https://github.com/erickherreraresearch/TaxonomyPureVisualMonocularSLAM). The selected methods and their codifications are listed in Table 1:
### Table 1. Selected methods
| Method | Codification | Category | Github Repository |
| --- | --- | --- | --- |
| ORB-SLAM2 | orb2_bw ; orb2_fw | classic + sparse + indirect | [code](https://github.com/raulmur/ORB_SLAM2) |
| DF-ORB-SLAM | df-orb_bw ; df-orb_fw | classic + dense + indirect | [code](https://github.com/834810269/DF-ORB-SLAM) |
| LSD-SLAM | lsd_bw ; lsd_fw | classic + dense + direct | [code](https://github.com/tum-vision/lsd_slam) |
| DSO | dso_bw ; dso_fw | classic + sparse + direct | [code](https://github.com/JakobEngel/dso) |
| SVO | svo_bw ; svo_fw | classic + sparse + hybrid | [code](https://github.com/uzh-rpg/rpg_svo) |
| LDSO | ldso_bw ; ldso_fw | classic + sparse + direct | [code](https://github.com/tum-vision/LDSO) |
| DSM | dsm_bw ; dsm_fw | classic + sparse + direct | [code](https://github.com/jzubizarreta/dsm) |
| DynaSLAM | dyna_bw ; dyna_fw | ml + sparse + indirect | [code](https://github.com/BertaBescos/DynaSLAM) |
| CNN-DSO | cnn-dso_bw ; cnn-dso_fw | ml + sparse + direct | [code](https://github.com/muskie82/CNN-DSO) |
| CNN-SVO | cnn-svo_bw ; cnn-svo_fw | ml + sparse + hybrid | [code](https://github.com/yan99033/CNN-SVO) |

Each method was implemented following the instructions provided in each official repository. The algorithms were evaluated using the monocular benchmark TUM-Mono of (Engel, Usenko, & Cremers, 2016) [see open source code](https://cvg.cit.tum.de/data/datasets/mono-dataset). In the experimental stage, each algorithm was executed ten times forward and ten times backward on each of the 50 sequences of the TUM-Mono dataset. The estimated trajectories for the ten algorithms are provided as suplementarý .zip files in this repository.

In addition, we provide sample videos of the execution of each algorithm. As examples for indoor sequences, we selected sequence_01 of the TUM-Mono dataset, whereas for outdoor performance, we selected sequence_29.

# ORB-SLAM2
### Sequence 01 (indoor)
[![Watch the video](https://img.youtube.com/vi/MFlmBsxEDKE/hqdefault.jpg)](https://youtu.be/MFlmBsxEDKE)
### Sequence 29 (outdoor)
[![Watch the video2](https://img.youtube.com/vi/sTZ1BpIZ2_A/hqdefault.jpg)](https://youtu.be/sTZ1BpIZ2_A)

# LSD-SLAM
### Sequence 01 (indoor)
[![Watch the video](https://img.youtube.com/vi/M5xZB6oBolM/hqdefault.jpg)](https://youtu.be/M5xZB6oBolM)
### Sequence 29 (outdoor)
[![Watch the video2](https://img.youtube.com/vi/K08h44ldZz0/hqdefault.jpg)](https://youtu.be/K08h44ldZz0)

# DSO
### Sequence 01 (indoor)
[![Watch the video](https://img.youtube.com/vi/FOXPWZppwKk/hqdefault.jpg)](https://youtu.be/FOXPWZppwKk)
### Sequence 29 (outdoor)
[![Watch the video2](https://img.youtube.com/vi/bU8uuTU9uUk/hqdefault.jpg)](https://youtu.be/bU8uuTU9uUk)

# SVO
### Sequence 01 (indoor)
[![Watch the video](https://img.youtube.com/vi/zqmbuCIR2Ls/hqdefault.jpg)](https://youtu.be/zqmbuCIR2Ls)
### Sequence 29 (outdoor)
[![Watch the video2](https://img.youtube.com/vi/OJt4YLaBJZk/hqdefault.jpg)](https://youtu.be/OJt4YLaBJZk)

# LDSO
### Sequence 01 (indoor)
[![Watch the video](https://img.youtube.com/vi/4Baucx413Y0/hqdefault.jpg)](https://youtu.be/4Baucx413Y0)
### Sequence 29 (outdoor)
[![Watch the video2](https://img.youtube.com/vi/VGuig4gwE98/hqdefault.jpg)](https://youtu.be/VGuig4gwE98)

# DSM
### Sequence 01 (indoor)
[![Watch the video](https://img.youtube.com/vi/ltKNP0d1d9E/hqdefault.jpg)](https://youtu.be/ltKNP0d1d9E)
### Sequence 29 (outdoor)
[![Watch the video2](https://img.youtube.com/vi/1h_pUdWEdKU/hqdefault.jpg)](https://youtu.be/1h_pUdWEdKU)

# DynaSLAM
### Sequence 01 (indoor)
[![Watch the video](https://img.youtube.com/vi/_0E0VL1mOCA/hqdefault.jpg)](https://youtu.be/_0E0VL1mOCA)
### Sequence 29 (outdoor)
[![Watch the video2](https://img.youtube.com/vi/GZIZbHqwo6g/hqdefault.jpg)](https://youtu.be/GZIZbHqwo6g)

# CNN-DSO
### Sequence 01 (indoor)
[![Watch the video](https://img.youtube.com/vi/vBa5EHLEbIA/hqdefault.jpg)](https://youtu.be/vBa5EHLEbIA)
### Sequence 29 (outdoor)
[![Watch the video2](https://img.youtube.com/vi/R9UbeKTBEiY/hqdefault.jpg)](https://youtu.be/R9UbeKTBEiY)

# CNN-SVO
### Sequence 01 (indoor)
[![Watch the video](https://img.youtube.com/vi/hBLDDXbTzys/hqdefault.jpg)](https://youtu.be/hBLDDXbTzys)
### Sequence 29 (outdoor)
[![Watch the video2](https://img.youtube.com/vi/RRa4fTd16wM/hqdefault.jpg)](https://youtu.be/RRa4fTd16wM)
