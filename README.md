# TEM Particle Tracking: Image Processing and Computer Vision Analysis

## Overview
To start, it's important to note that the video showcased is not a representation of the work I completed during my professional endeavors. I selected this particular video due to its confidential content.  The primary goal is to demonstrate and highlight my skills.

## Objective
The primary aim of this project is to track the individual growth of particles over time and analyze the resulting trends. In real-world scenarios, particles often undergo nucleation, a process where small particles form and grow. Understanding the nucleation process is crucial for comprehending the overall particle growth dynamics. Additionally, the project aims to investigate instances where particles exhibit sudden size changes, attributed to chemical processes. 

The goal is to identify and analyze the reasons behind such fluctuations, whether it be an increase or decrease in particle size, providing valuable insights into the underlying chemical phenomena influencing particle behavior. The tracking mechanism employed in this study enables the observation of nucleation events and facilitates a comprehensive analysis of the factors contributing to particle growth or shrinkage over time.

## Methodology
The methodology for this project involves a multi-step process:

1. **Video Preprocessing:**
Image Annotation is conducted using  [LabKit](https://imagej.net/plugins/labkit/). Given the rarity of the particles, utilizing a pre-trained model is not feasible. Hence, a self-annotation approach is adopted, where a small subset of the frames is manually annotated. The selection of frames for annotation depends on the characteristics of the dataset. The purpose of self-annotation is to generate an accurate binary mask, which can then be utilized for training purposes.
     
2. **Image-to-Image Translation**
   [CycleGAN](https://arxiv.org/abs/1703.10593) and [Pix2pixGAN](https://arxiv.org/abs/1611.07004) is utilized for training. The difference between CycleGan and pix2pix GAN is that pix2pix gan required paired dataset while c

3. **Particle Tracking:**
   - Utilizing computer vision algorithms to track the movement and growth of individual particles across frames.

4. **Feature Extraction:**
   - Extracting key features, such as particle size and shape, for each tracked particle.

5. **Data Analysis:**
   - Analyzing the extracted data to identify trends, especially focusing on nucleation events and sudden size changes.

The methodology is designed to provide a robust framework for understanding particle behavior and trends over time.

## Demo
#### Binary Mask

![merge_mask](https://github.com/AsherTeo/TEM-Visionary---Processing-and-Analysis-Tools-for-Electron-Microscopy/assets/78581569/6493b8ff-1a73-447f-ac83-9ef98252b83d)

#### Tracking
![merge1](https://github.com/AsherTeo/TEM-Visionary---Processing-and-Analysis-Tools-for-Electron-Microscopy/assets/78581569/6a86bdf8-7c36-4e63-ba6e-006f218e6096)

## Data Download

For a demonstration of the project, you can download the video  [here](https://onlinelibrary.wiley.com/action/downloadSupplement?doi=10.1002%2Fadfm.202104628&file=adfm202104628-sup-0002-VideoS1.avi). Please note that this video is used solely for illustrative purposes and does not contain the actual code or proprietary content of the project.

The video is associated with the article titled "Multilayer Graphene—A Promising Electrode Material in Liquid Cell Electrochemistry" published in [Advanced Functional Materials](https://onlinelibrary.wiley.com/doi/abs/10.1002/adfm.202104628) by Tan Shu Fen. If you are interested in exploring the full context and details of the project, I recommend referring to the original article.  

If you have any questions or would like to discuss the project further, feel free to reach out.

