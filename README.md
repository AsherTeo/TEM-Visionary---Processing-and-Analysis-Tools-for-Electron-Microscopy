# TEM Particle Tracking: Image Processing and Computer Vision Analysis

## Overview
To start, it's important to note that the video showcased is not a representation of the work I completed during my professional endeavors. I selected this particular video due to its confidential content.  The primary goal is to demonstrate and highlight my skills.

The primary aim of this project is to track the individual growth of particles over time and analyze the resulting trends. In real-world scenarios, particles often undergo nucleation, a process where small particles form and grow. Understanding the nucleation process is crucial for comprehending the overall particle growth dynamics. Additionally, the project aims to investigate instances where particles exhibit sudden size changes, attributed to chemical processes. 

## Objective
The goal is to identify and analyze the reasons behind such fluctuations, whether it be an increase or decrease in particle size, providing valuable insights into the underlying chemical phenomena influencing particle behavior. The tracking mechanism employed in this study enables the observation of nucleation events and facilitates a comprehensive analysis of the factors contributing to particle growth or shrinkage over time.

## Methodology
The methodology for this project involves a multi-step process:

1. **Video Preprocessing:**
Image Annotation is conducted using  [LabKit](https://imagej.net/plugins/labkit/). Given the rarity of the particles, utilizing a pre-trained model is not feasible. Hence, a self-annotation approach is adopted, where a small subset of the frames is manually annotated. The selection of frames for annotation depends on the characteristics of the dataset. The purpose of self-annotation is to generate an accurate binary mask, which can then be utilized for training purposes.
     
2. **Image-to-Image Translation**
The training process employs [Pix2pixGAN](https://arxiv.org/abs/1611.07004) , specifically designed for paired image-to-image translation tasks. This model is trained using a dataset consisting of input images (frames) and their corresponding targets (binary masks). By utilizing a small subset of annotated masks during training, Pix2pixGAN learns the necessary mapping, enabling its application to the remaining unannotated frames.

3. **Image Processing**
After the Pix2pixGAN training, some of the generated masks may exhibit discoloration. To address this, an additional step is implemented using OpenCV to convert these masks into binary format. This post-processing ensures uniformity and accuracy in the binary masks, enhancing their suitability for subsequent stages of the analysis.

4. **Particle Tracking:**
A class is designed for object tracking in a video, utilizing the Euclidean distance to monitor the positions of detected objects. It assigns unique IDs to objects based on their movement across frames, maintaining and updating their center positions as new frames are processed. In the case of a newly detected object, the class either updates the existing object's position or assigns a new ID. There are two types of methods employed to identify particles: one utilizes a unique index, and the other adds unique colors. The unique color method is particularly advantageous for easy identification. The class ensures effective object tracking using the Euclidean distance metric and manages the cleanup of unused IDs.

5. **Data Analysis:**
In real-world scenarios, numerous videos showcase diverse parameters, including different scan rates and various types of carbon-based nanomaterials. Employing object tracking in these videos enables us to uncover patterns and refine our comprehension of nucleation. This analytical process is further enhanced by leveraging Python data visualization libraries such as Seaborn, allowing for a more effective and visually informative exploration of the tracked data. This approach gets us closer to understanding the underlying problem

## Demo
#### Example of Binary Mask generated using Pix2pix GAN

![merge_mask](https://github.com/AsherTeo/TEM-Visionary---Processing-and-Analysis-Tools-for-Electron-Microscopy/assets/78581569/6493b8ff-1a73-447f-ac83-9ef98252b83d)

#### Example of Particle Tracking with unique ID and colors
![merge1](https://github.com/AsherTeo/TEM-Visionary---Processing-and-Analysis-Tools-for-Electron-Microscopy/assets/78581569/6a86bdf8-7c36-4e63-ba6e-006f218e6096)

!![Picture1](https://github.com/AsherTeo/TEM-Visionary---Processing-and-Analysis-Tools-for-Electron-Microscopy/assets/78581569/9deec9e7-5a15-4677-96f6-ba93eb29bd03) ![Picture2](https://github.com/AsherTeo/TEM-Visionary---Processing-and-Analysis-Tools-for-Electron-Microscopy/assets/78581569/4f81ec4a-3351-44c1-be16-32fce2dd474f)

## Data Download

For a demonstration of the project, you can download the video  [here](https://onlinelibrary.wiley.com/action/downloadSupplement?doi=10.1002%2Fadfm.202104628&file=adfm202104628-sup-0002-VideoS1.avi). Please note that this video is used solely for illustrative purposes and does not contain the actual code or proprietary content of the project.

The video is associated with the article titled "Multilayer Graphene—A Promising Electrode Material in Liquid Cell Electrochemistry" published in [Advanced Functional Materials](https://onlinelibrary.wiley.com/doi/abs/10.1002/adfm.202104628) by Tan Shu Fen. If you are interested in exploring the full context and details of the project, I recommend referring to the original article.  

If you have any questions or would like to discuss the project further, feel free to reach out.

