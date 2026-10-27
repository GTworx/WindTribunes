---
title: "Wind turbine blades surface defect high-quality image dataset construction and performance validation"
source: "https://www.nature.com/articles/s41597-026-07455-1"
author:
  - "[[Ruihua Zhang]]"
  - "[[Sunxin Wang]]"
  - "[[Sheng Liu]]"
  - "[[Yu Liang]]"
  - "[[Taoyu Wang]]"
  - "[[Chao Liu]]"
  - "[[Shu Chen]]"
published: 2026-05-20
created: 2026-10-25
description: "Aiming at the actual scenario of wind farm, this research releases a wind turbine blades surface defect dataset named WTBs2025. The images in this dataset are captured from the wind farm sites and then preprocessed for the following data augmentation. However, due to the small number of lightning strike defect samples, data augmentation based on GA-DCGAN is performed, after some simple augmentation strategies. WTBs2025 has a total of 7544 blade defect images covering 9 wind turbine blade defect types. WTBs2025 is characterized by its diverse defect types, extensive collection of defect images across multiple categories, and well-established features. These features include broad defect coverage, high-quality annotations, standardized data formats, and multi-scenario applicability. WTBs2025 demonstrates its unique practical value in the wind turbine blade damage object detection field under its high degree of compatibility and specificity. Experiments show that this dataset performs well on several well-known object detection models and provides valuable image data resources for the research and application of wind turbine blade damage detection and other directions."
tags:
  - "clippings"
---
## Abstract

Aiming at the actual scenario of wind farm, this research releases a wind turbine blades surface defect dataset named WTBs2025. The images in this dataset are captured from the wind farm sites and then preprocessed for the following data augmentation. However, due to the small number of lightning strike defect samples, data augmentation based on GA-DCGAN is performed, after some simple augmentation strategies. WTBs2025 has a total of 7544 blade defect images covering 9 wind turbine blade defect types. WTBs2025 is characterized by its diverse defect types, extensive collection of defect images across multiple categories, and well-established features. These features include broad defect coverage, high-quality annotations, standardized data formats, and multi-scenario applicability. WTBs2025 demonstrates its unique practical value in the wind turbine blade damage object detection field under its high degree of compatibility and specificity. Experiments show that this dataset performs well on several well-known object detection models and provides valuable image data resources for the research and application of wind turbine blade damage detection and other directions.

## Background & Summary

In the context of the global energy transition, wind power has become one of the fastest-growing renewable energy sources [^1] [^2]. Under the guidance of carbon peak and carbon neutrality goals, China’s wind turbine capacity and blade diameter continue to make breakthroughs. The efficient and stable operational performance of wind turbines is an important support for high-performance power generation, and these characteristics make them an indispensable part of the renewable energy power generation sector. The global wind power industry continues to grow through 2025, WTBs market has expanded accordingly [^3]. China’s installed wind power capacity and power generation are among the world’s largest, making it one of the largest wind power markets in the world [^4]. By the end of June 2025, the cumulative grid-connected capacity of wind power in China had reached 467 million kW, an increase of 20% year-on-year. With the increasing global demand for clean energy and the continuous progress of technology, the WTB industry will usher in a broader development prospect [^5]. However, due to the complexity of processing, transportation, installation, and operation environment, WTBs’ surface damage is inevitable. If these damages cannot be repaired in time, they will have a certain negative impact on the safety and efficiency of wind turbines. Multiple studies show that WTBs are the key component of wind turbines. Their cost accounts for around 20% of the total cost, and the accident rate accounts for 30% of the total accidents. Accidents caused by blade defect occur from time to time and can result in significant economic and property damage and even injuries [^6] [^7].

Traditional blade damage detection mostly means manual visual inspection [^8], mainly including blade maintenance platform inspection, rope drop inspection, and high-power telescope inspection. These methods have the disadvantages of low efficiency, high cost, and dangerous operation. Current blade damage detection technologies primarily rely on sensor-based approaches, including ultrasonic flaw detection [^9], acoustic emission signal monitoring [^10], vibration signal analysis [^11], and fiber optic sensing detection [^12], etc. To overcome the long-standing challenges of repair effects and domain shift in structural health monitoring, Gardner *et al*.[^13] proposed a metric-informed transfer learning framework that explicitly incorporates damage-sensitive metrics into the transfer process. This method enables effective knowledge transfer across different structural states, including pre- and post-repair conditions, and significantly improves the robustness and generalization ability of damage diagnosis under changing operational environments. Furthermore, Erazo *et al*.[^14] conducted a systematic critical review of structural health monitoring (SHM) under environmental and operational variability, summarizing effective approaches for baseline compensation and reference-free techniques. To facilitate the validation of such algorithms, high-quality benchmark datasets have also been introduced, such as the wind turbine condition monitoring dataset released by the Fraunhofer LBF [^15]. These methods have achieved barely acceptable results for blade damage detection to a certain extent. However, there are different degrees of problems, such as high installation and maintenance costs of sensors, sensitivity to environmental conditions, and complex data processing and analysis processes. With the continuous update and development of Unmanned Aerial Vehicle (UAV) and computer vision technology, using UAV for WTB fault detection is a direction of concern in the research of WTB inspection technology [^16] [^17]. However, the construction of effective datasets in this field has become the main bottleneck that restricts its development. Early studies mostly rely on synthetic data or small-scale datasets collected in laboratory environments (e.g., only hundreds of images). These datasets have poor generalization ability, such as a single defect type and a lack of multi-view real scene data.

### Applications and challenges

UAV and robot have been used in wind turbine blade inspection to collect image data through high-resolution cameras or infrared thermal imaging devices [^18]. Using the data collected by UAV and robot to train a deep learning neural network can improve the defect recognition ability. The process of WTB surface defect detection becomes more and more automated and intelligent with the never-ending development of the neural network theory. The accuracy can reach a certain level that can reduce the cost of manual inspection [^19]. However, there are still many challenges in this field, limited by problems such as data collection, data annotation, and generalization ability:

1. The difficulty of data collection. The collection of blade surface defect data is usually carried out at high altitudes or in harsh environments. Limited by climatic conditions (wind speed, light, rain, and snow, etc.), it is difficult to collect clear and complete images [^20].
2. The complication of defect types and data annotation. The types of blade surface defects are diverse, including paint crack, erosion, coating detachment, and lightning strike, etc. Each defect has different performance under various lighting and angles, which decreases the accuracy of detection [^21].
3. The problem of unbalanced data. Some defects (e.g., lightning strike) are scarce, resulting in unbalanced datasets that affect model learning.

### Contributions of this research

To improve the efficiency of wind farm operation and maintenance, and to promote industrial intelligent production, this research constructs WTBs2025 specifically for WTB defect detection and identification. The necessity and validity of WTBs2025 are analyzed to verify the dataset’s relevance, irreplaceability, and practical application in specific scenarios. The main contributions of this paper are as follows:

1. Dataset collecting and preprocessing: First, the data are obtained from the blade inspection reports of wind farm turbine blades. Defects such as lightning strike, protective film damage, oil leakages, erosion, and other defects are established. Second, data cleaning is performed to remove duplicate images and blurred images. Next, various damage types are marked using an annotation tool. At last, data augmentation is performed on the original data to expand the dataset.
2. Expansion and construction of WTBs2025: Due to the low frequency of lightning strike, the available data is limited. Simple augmentation is performed by rotating, changing brightness, and mirroring, followed by data augmentation using Gaussian-Attention Deep Convolution Generative Adversarial Networks (GA-DCGAN). By generating high-quality and diverse synthetic data, the number of training samples can be increased, thereby alleviating issues of overfitting or underfitting caused by insufficient data. After the above steps, the size of WTBs2025 reaches 7,544 images.
3. Dataset validation: The quality and availability of the dataset are confirmed by technical validation, which includes different popular deep learning models. This provides researchers with sufficient experimental data for future research.

The technology path is shown in Fig. [1](https://www.nature.com/articles/s41597-026-07455-1#Fig1).

**Fig. 1**

![Fig. 1](https://media.springernature.com/lw685/springer-static/image/art%3A10.1038%2Fs41597-026-07455-1/MediaObjects/41597_2026_7455_Fig1_HTML.png?as=webp)

[Full size image](https://www.nature.com/articles/s41597-026-07455-1/figures/1)

Technology path.

Original WTBs2025 is comprised of 7316 annotated images covering nine defect types: paint crack (447 images), protective film damage (549 images), lightning strike (57 images), coating detachment (1085 images), erosion (2799 images), oil leakage (520 images), pinhole (569 images), surface stain (263 images), and localized damage (1027 images). Among them, the number of lightning strike reaches 285 after two augmentations, and there are 7544 images in WTBs2025. This dataset is of great value for projects focused on surface defect detection of WTB. Distribution of original WTBs2025 defect types is shown in Fig. [2](https://www.nature.com/articles/s41597-026-07455-1#Fig2), where lightning strike defects account for only 1% of the total.

**Fig. 2**

![Fig. 2](https://media.springernature.com/lw685/springer-static/image/art%3A10.1038%2Fs41597-026-07455-1/MediaObjects/41597_2026_7455_Fig2_HTML.png?as=webp)

[Full size image](https://www.nature.com/articles/s41597-026-07455-1/figures/2)

Distribution of original WTBs2025 defect types.

## Methods

The development of WTBs2025 mainly consists of four phases: data collection, data preprocessing, data augmentation, and data annotation. The details of each stage in the workflow are as follows:

### Data collection

The images included in the WTBs2025 dataset were acquired during routine inspection campaigns conducted at multiple onshore wind farms located in Shanxi, Gansu, and Shaanxi provinces, China. Image acquisition was carried out using Survey3W Visible Light RGB cameras operated at close range by trained inspection personnel under real-world operational conditions of wind turbines. The resolution of the original image is 4000 × 3000 pixels, which allowed for reliable visualization of wind turbine blade surface defects across different spatial scales. Data collection was performed over multiple inspection periods between 2022 and 2024, encompassing a wide range of practical inspection scenarios encountered in wind farm operation and maintenance activities. The construction of the WTBs2025 dataset was completed in 2025. Specifically, representative data were collected during midday inspections in the spring of 2022 and the summer of 2023, with approximate illumination intensities of 70000 lux and 85000 lux, respectively. During the data acquisition process, images were collected under diverse environmental conditions, including different illumination levels (e.g., strong sunlight, overcast conditions, and partial shadows), varying weather conditions, and complex background scenarios such as sky-dominated backgrounds, blade–tower intersections, and surrounding terrain. This environmental diversity enhances the representativeness of the dataset and supports robust evaluation of defect detection models under realistic operating conditions. The filtering mainly considers the following cases: low-quality data removal, duplicate data removal, and invalid data screening.

### Data preprocessing

To ensure data consistency and compatibility across different training frameworks, all images in the WTBs2025 dataset were converted to the JPG format during preprocessing. Although JPG employs lossy compression, it provides a favorable trade-off between storage efficiency and visual fidelity, which is particularly suitable for large-scale datasets. Given that the considered wind turbine blade surface defects are mainly characterized by macroscopic structural patterns rather than subtle pixel-level details, the impact of JPG compression on defect representation is negligible. Furthermore, all images were uniformly resized to 640 × 640 pixels to standardize the model input resolution. This strategy avoids potential inconsistencies caused by variable image sizes and prevents implicit rescaling operations within neural networks, which may introduce scale distortion or uncontrolled information loss. By adopting a unified resolution, the preprocessing pipeline is simplified, GPU training efficiency is improved, and data augmentation operations can be applied more consistently, thereby enhancing the generalization capability of the trained models. The data preprocessing and cleaning procedures were conducted with reference to the ISO/IEC 25012 data quality model, ensuring accuracy, consistency, and reliability throughout the dataset construction process.

### Data augmentation

The original number of lightning strike images in WTBs2025 is only 57, while there are hundreds or even thousands of images for other defect types. In WTB defect types, lightning strike images are collected from very limited real samples, which leads to an unbalanced distribution of data for model training. The object detection model may not learn enough features, resulting in a degradation of detection performance. Among all defect categories in WTBs2025, lightning strike exhibits the most severe data scarcity and the highest class imbalance, while other defect types still retain sufficient sample sizes for stable model training. To avoid introducing unnecessary distribution shifts and to enable a controlled evaluation of data augmentation effectiveness, GAN-based augmentation is applied exclusively to the lightning strike class. This design choice allows the impact of GA-DCGAN on alleviating extreme imbalance to be analyzed independently, without confounding effects from simultaneous augmentation of multiple defect categories.

For these reasons, we perform simple augmentation by changing brightness, mirroring, and rotation to expand the data to 228 images, shown in Fig. [3](https://www.nature.com/articles/s41597-026-07455-1#Fig3). Data augmentation based on an improved DCGAN, named GA-DCGAN, is utilized. First, a Convolutional Block Attention Module (CBAM) is added after each convolutional layer of the generator and discriminator in DCGAN; second, a Gaussian sharpening layer is added at the end of the generator to improve the quality and clarity of the generated images.

**Fig. 3**

![Fig. 3](https://media.springernature.com/lw685/springer-static/image/art%3A10.1038%2Fs41597-026-07455-1/MediaObjects/41597_2026_7455_Fig3_HTML.png?as=webp)

[Full size image](https://www.nature.com/articles/s41597-026-07455-1/figures/3)

Simple augmentation **(a)** Original image **(b)** Mirrored image. **(c)** Changed brightness image **(d)** Rotated image.

GA-DCGAN generates diverse and realistic defect images by learning from existing lightning strike data to make up for the insufficient data problem. Finally, 57 images of lightning strike are generated, which make up part of the total of 285 images of lightning strike defect types.

### Expand the unbalanced data types by GA-DCGAN

Although primary data augmentation methods are simple and easy to implement, these operations can only increase the number of samples in the dataset. If only conducting primary data augmentation, the sample diversity of the dataset is not significantly improved, thus the detection performance of the neural network is still limited. In the field of image data augmentation, GANs proposed based on the idea of adversarial training can generate high-quality images. It is widely used in data augmentation tasks and has been used to derive many GAN variant models with excellent performance. DCGAN was proposed by Radford *et al*.[^22] in 2015, which is an advanced generative model among many derived models. The DCGAN structure is shown in Fig. [4](https://www.nature.com/articles/s41597-026-07455-1#Fig4). While the efficiency of network training and the quality of generated images have seen notable improvements, challenges such as training instability and the production of numerous low-quality images remain unresolved.

1. GA-DCGAN Generator and Discriminator architecture

**Fig. 4**

![Fig. 4](https://media.springernature.com/lw685/springer-static/image/art%3A10.1038%2Fs41597-026-07455-1/MediaObjects/41597_2026_7455_Fig4_HTML.png?as=webp)

[Full size image](https://www.nature.com/articles/s41597-026-07455-1/figures/4)

DCGAN Network Structure.

To solve the problems of low-quality images generated by DCGAN and unstable network training, the CBAM attention mechanism is introduced in the generator to add attention to different features, making the generation process more efficient and accurate. Specifically, the CBAM module is integrated at different positions in the generator and discriminator according to their functional roles. In the generator, CBAM is inserted after the Batch Normalization (BN) layer in each convolutional block, enabling attention-guided refinement of normalized feature maps before activation and upsampling. In the discriminator, CBAM is placed after the LeakyReLU activation, allowing the network to emphasize discriminative features after non-linear transformation and improve feature selection before subsequent downsampling and classification. At the same time, a Gaussian sharpening module is added to make the edges and textures of the image more obvious, thus improving visual effects. After the primary augmentation, GA-DCGAN is used for the secondary augmentation. Figure [5](https://www.nature.com/articles/s41597-026-07455-1#Fig5) shows the network structure of GA-DCGAN.

1. Model evaluation metrics

**Fig. 5**

![Fig. 5](https://media.springernature.com/lw685/springer-static/image/art%3A10.1038%2Fs41597-026-07455-1/MediaObjects/41597_2026_7455_Fig5_HTML.png?as=webp)

[Full size image](https://www.nature.com/articles/s41597-026-07455-1/figures/5)

GA-DCGAN Network Structure.

To comprehensively evaluate the quality of the generated images, this study employs three complementary quantitative metrics: Peak Signal-to-Noise Ratio (PSNR) [^23], Structural Similarity Index Measure (SSIM) [^24], and Learned Perceptual Image Patch Similarity (LPIPS) [^25]. Since the generated images are paired one-to-one with their corresponding real images, these pixel-level and perceptual-level metrics are particularly well-suited for this evaluation scenario. PSNR is a classical image quality metric that measures pixel-level fidelity between a generated image and its corresponding real image. It is defined based on the Mean Squared Error (MSE) between the two images, as shown in formula (1) and (2):

$$
MSE=\frac{1}{HW}\mathop{\sum }\limits_{i=1}^{H}\mathop{\sum }\limits_{j=1}^{W}{[I(i,j)-\hat{I}(i,j)]}^{2}
$$

(1)

$$
PSNR=10\cdot {\log }_{10}\left(\frac{MA{X}_{I}^{2}}{MSE}\right)
$$

(2)

where $MA{X}_{I}$ denotes the maximum possible pixel value (255 for 8-bit images), and $H,W$ are the height and width of the image, respectively. PSNR is expressed in decibels (dB), and higher values indicate greater pixel-level similarity between the generated and real images. Generally, a PSNR above 30 dB is considered to indicate high fidelity, while values below 20 dB suggest significant distortion.

SSIM is a perceptually motivated metric that evaluates image similarity from three complementary aspects: luminance, contrast, and structure. Unlike PSNR, which treats all pixel errors equally, SSIM is designed to be more consistent with the human visual system. Given a real image and a generated image, SSIM is computed as shown in formula (3):

$$
SSIM(I,\hat{I})=\frac{(2{\mu }_{I}{\mu }_{\hat{I}}+{C}_{1})(2{\sigma }_{I\hat{I}}+{C}_{2})}{({\mu }_{I}^{2}+{\mu }_{\hat{I}}^{2}+{C}_{1})({\sigma }_{I}^{2}+{\sigma }_{\hat{I}}^{2}+{C}_{2})}
$$

(3)

where ${\mu }_{I}$ and ${\mu }_{\hat{I}}$ are the local mean intensities, ${\sigma }_{I}^{2}$ and ${\sigma }_{\hat{I}}^{2}$ are the local variances, ${\sigma }_{I\hat{I}}$ is the cross-covariance, and ${C}_{1}$, ${C}_{2}$ are small stabilizing constants to avoid division by zero. SSIM values range from 0 to 1, where 1 indicates perfect structural consistency. Higher SSIM values reflect better preservation of structural and textural information in the generated images.

LPIPS is introduced as a deep perceptual similarity metric that measures image-level differences by comparing feature representations extracted from pretrained neural networks, rather than relying solely on pixel-level statistics. LPIPS has been demonstrated to correlate strongly with human perceptual judgments and is particularly effective in capturing fine-grained structural and texture consistency. Given two images, LPIPS is computed as shown in formula (4):

$$
LPIPS(I,\hat{I})=\sum _{l}\frac{1}{{H}_{l}{W}_{l}}\sum _{h,w}{\Vert {w}_{l}\odot ({\phi }_{l}{(I)}_{hw}-{\phi }_{l}{(\hat{I})}_{hw})\Vert }_{2}^{2}
$$

(4)

where ${\phi }_{l}$ denotes the feature map extracted from the $l-th$ layer of a pretrained network (AlexNet in this study), ${H}_{l}$ and ${w}_{l}$ are the spatial dimensions of the feature map at layer $l$, and ${w}_{l}$ represents learned channel-wise weights. Lower LPIPS values indicate higher perceptual similarity and better visual fidelity.

By jointly employing PSNR, SSIM, and LPIPS, this study achieves a comprehensive evaluation that spans pixel-level accuracy, structural consistency, and deep perceptual quality. The three metrics are complementary: PSNR captures low-level pixel fidelity, SSIM reflects structural and luminance consistency, and LPIPS provides perceptual-level assessment aligned with human visual judgment. This multi-metric framework ensures a more reliable and thorough evaluation of the generative model’s performance.

1. Construction of DCGAN experimental environment

In this research, Python and TensorFlow are used to build DCGAN model and GA-DCGAN. The experimental environment is shown in Table [1](https://www.nature.com/articles/s41597-026-07455-1#Tab1).

**Table 1 DCGAN Experimental environment.**

The network is trained for 10000 epochs, with a batch size of 4, an optimizer as Adam, and a learning rate of 0.002. The generative training process of DCGAN and GA-DCGAN is shown in Fig. [6](https://www.nature.com/articles/s41597-026-07455-1#Fig6).

**Fig. 6**

![Fig. 6](https://media.springernature.com/lw685/springer-static/image/art%3A10.1038%2Fs41597-026-07455-1/MediaObjects/41597_2026_7455_Fig6_HTML.png?as=webp)

[Full size image](https://www.nature.com/articles/s41597-026-07455-1/figures/6)

Generative training process of DCGAN and GA-DCGAN.

The experimental results show that when the iteration epoch reaches 5000, the images generated by DCGAN and GA-DCGAN have rough contours, thus they can hardly be used as extended defect samples. As the number of iterations increases, DCGAN tends to generate noisy images due to unstable training, whereas GA-DCGAN continues to produce images that progressively resemble real defect images. When the number of training epochs reaches 10000, both models are capable of generating usable defect images. However, the shapes generated by GA-DCGAN are closer to real images, and the image quality is higher. Ultimately, GA-DCGAN generates 57 lightning strike images and extends the lightning strike damage data to 285 images.

### Ablation experiment

To verify the effectiveness of the added modules, ablation experiments are carried out in the same environment, and different modules are added based on the DCGAN model. Ablation experimental results show that the added modules are helpful in improving the performance and generating better surface defect samples. The ablation experiment is shown in Table [2](https://www.nature.com/articles/s41597-026-07455-1#Tab2).

**Table 2 Ablation experiment.**

As reported in Table [2](https://www.nature.com/articles/s41597-026-07455-1#Tab2), the baseline DCGAN model yields a PSNR of 18.23 dB, an SSIM of 0.3812, and an LPIPS of 0.8218, indicating poor pixel-level fidelity, weak structural consistency, and substantial perceptual deviation from real samples. After introducing the CBAM attention module, the PSNR increases to 24.67 dB and the SSIM improves to 0.6153, while the LPIPS decreases markedly to 0.2834, demonstrating that channel and spatial attention mechanisms effectively enhance both the structural integrity and perceptual quality of the generated images. When both CBAM and the Gaussian diffusion mechanism are incorporated into the full model, the PSNR is further elevated to 28.34 dB, the SSIM reaches 0.7826, and the LPIPS is reduced to 0.1011, reflecting consistent and substantial improvements across all three evaluation dimensions. Generally, a PSNR approaching 30 dB indicates high pixel-level reconstruction accuracy, an SSIM above 0.75 reflects strong structural similarity, and an LPIPS value close to 0.10 corresponds to perceptual quality that closely aligns with human visual judgment. Therefore, the final configuration incorporating both CBAM and the Gaussian diffusion mechanism achieves high-quality and visually realistic defect image generation, validating the complementary contributions of each proposed component.

### Data annotation

The damage types of WTB mainly include paint crack, protective film damage, lightning strike, coating detachment, erosion, oil leakage, pinhole, surface stain, and localized damage. Using the LabelImg annotation tool, a minimal rectangular box is drawn for each injury on each image in the WTBs2025, along with the injury category to which they belonged. Each batch of images was independently annotated by two individuals, and the annotations were subsequently compared and verified by the authors to minimize subjective bias and ensure the reliability and quality of the dataset. Subsequently, the annotated image labels are saved in TXT format in a folder in order. The data annotation is shown in Fig. [7](https://www.nature.com/articles/s41597-026-07455-1#Fig7).

**Fig. 7**

![Fig. 7](https://media.springernature.com/lw685/springer-static/image/art%3A10.1038%2Fs41597-026-07455-1/MediaObjects/41597_2026_7455_Fig7_HTML.png?as=webp)

[Full size image](https://www.nature.com/articles/s41597-026-07455-1/figures/7)

Data annotation. **(a)** Crack **(b)** Lightning strike **(c)** Surface stain. **(d)** Coating detachment **(e)** Protective film damage **(f)** Oil leakage **(g)** Pinhole. **(h)** Erosion **(i)** Localized damage.

## Data Records

WTBs2025 is uploaded to the public figshare [^26] repository as a zip file. The file is divided into 9 directories for the 9 types of defects in WTB, namely paint crack, protective film damage, lightning strike, coating detachment, erosion, oil leakage, pinhole, surface stain, and localized damage. Each folder contains two subdirectories: images and labels. The images directory contains JPG-format images of various types of blade damage. The labels directory stores the label files of the corresponding image labels in TXT-format. The label files are numbered from 0 to 9 for each defect category, and the specific numbering information can be viewed in the data.yaml file under WTBs2025 root directory. The structure of WTBs2025 file is shown in Fig. [8](https://www.nature.com/articles/s41597-026-07455-1#Fig8). To facilitate clear usage and long-term reproducibility, a standardized dataset specification is provided. All images are stored in JPG format with a unified resolution of 640 × 640 pixels after preprocessing. Annotations follow the YOLO format, where each label file corresponds to one image and contains the class index and normalized bounding box coordinates. Each defect category is uniquely defined and consistently named according to its physical surface defect characteristics. The dataset adopts a unified naming convention for image–label pairs to ensure correct correspondence. WTBs2025 is released for research and academic use, and users are recommended to follow the dataset protocol provided in the repository for training, evaluation, and benchmarking purposes.

**Fig. 8**

![Fig. 8](https://media.springernature.com/lw685/springer-static/image/art%3A10.1038%2Fs41597-026-07455-1/MediaObjects/41597_2026_7455_Fig8_HTML.png?as=webp)

[Full size image](https://www.nature.com/articles/s41597-026-07455-1/figures/8)

Organization of the WTBs2025 file directory.

Each defect category in the dataset is organized into a separate folder to enable independent access and convenient management. The complete dataset has been made publicly available to facilitate transparency and reproducibility of the research, and can be accessed at [https://doi.org/10.6084/m9.figshare.28876391](https://doi.org/10.6084/m9.figshare.28876391).

## Technical Validation

### Comparison of related datasets

To verify the efficiency of object detection algorithms, this research compared multiple datasets in this field, aiming to provide insight for vision researchers to better develop, improve, and evaluate object detection algorithms. In the following, three commonly used datasets are analyzed and compared with WTBs2025.

In terms of categories, these datasets cover a variety of different categories, including WTB, aircraft, and ship defects. WTBs2025 focuses more on the detection of WTB damage and provides more specific application scenarios. In terms of the number of images, there are significant differences between these datasets. Compared with other datasets, WTBs2025 has certain advantages in the number of images, which provides sufficient data resources for researchers. A pair of different defect detection datasets is shown in Table [3](https://www.nature.com/articles/s41597-026-07455-1#Tab3).

**Table 3 Comparison of different defect datasets.**

### Verification method

According to their design principles, the current mainstream object detection algorithms can be divided into one-stage and two-stage. The former uses the feature extraction network to extract the feature information of the input image and directly completes the position information regression and category prediction. The latter generates candidate regions and classifies them to complete the detection task. One-stage detection algorithms mainly include You Only Look Once (YOLO) [^27] family and Single Shot MultiBox Detection (SSD) [^28]. Among them, the YOLO object detection algorithm has the characteristics of relatively fast detection speed, light network weight, and simple structure, making it the most used single-stage object detection algorithm. The two-stage detection algorithms mainly include R-CNN [^29], which has the characteristics of high accuracy and flexibility, making it suitable for tasks requiring high accuracy. In this experiment, object detection models provided above are selected to train and test the object detection task on WTBs2025.

### Experimental environment

The experimental environment is the Window10 system, and the model is implemented by the PyTorch framework. The specific experimental hardware environment is a 13th Gen Intel(R) Core (TM) i5-13490F processor and one NVIDIA GeForce RTX 4060 graphics card. The model is uniformly trained for 100 epochs with a Batch Size of 4 and an input image size of 640 × 640 pixels. The experimental environment for object detection algorithms is shown in Table [4](https://www.nature.com/articles/s41597-026-07455-1#Tab4).

**Table 4 Experimental environment for object detection algorithms.**

### Dataset configuration

In this experiment, a self-constructed WTBs2025 wind turbine blade surface defect dataset is employed for experimental evaluation. The dataset consists of 7,544 images. To ensure the reliability and fairness of the experimental results, the dataset is divided into training, validation, and test sets with a ratio of 7:2:1. Specifically, the training set is used for model learning and parameter optimization, the validation set is utilized to monitor the training process and prevent overfitting, and the test set is reserved for the final performance evaluation of the proposed method.

### Defect detection evaluation

In this experiment, Precision, Recall, and mean average precision mAP are used to evaluate the model. True Positives (TP) and True Negatives (TN) represent the correct prediction, where TP represents the correct detection of the object, and TN indicates a non-object correctly classified as non-object. False Positives (FP) and False Negatives (FN) denote mispredictions, where FP indicate a nonobject is incorrectly predicted as an object, and FN are failures to detect an object.

Where the Precision (P) is defined as the ratio between the number of samples correctly predicted as positive cases and the number of all samples predicted as positive cases. The formula is as (5):

$$
Precision=\frac{TP}{TP+FP}
$$

(5)

Recall (R) represents the proportion of all true positive case samples that the model can correctly predict as positive cases. The formula is as (6):

$$
Recall=\frac{TP}{TP+FN}
$$

(6)

Average Precision (AP) refers to the area enclosed by a curve consisting of Recall as the horizontal axis and Precision as the vertical axis. The formula is as (7):

$$
\begin{array}{c}AP=\mathop{\sum }\limits_{i=1}^{n-1}({r}_{i+1}-{r}_{i})p({r}_{i+1})\end{array}
$$

(7)

The mean Average Precision mAP in the experiment is the mean of the average precision of all the categories in the dataset. The formula is as (8):

$$
mAP=\frac{1}{m}\mathop{\sum }\limits_{i=1}^{m}A{P}_{i}
$$

(8)

where m denotes the total number of object categories.

The performance phenotype of the object detection algorithm on WTBs2025 is shown in Table [5](https://www.nature.com/articles/s41597-026-07455-1#Tab5).

**Table 5 Performance phenotype of the object detection algorithm on WTBs2025.**

There are 9 defect types in WTBs2025, and each defect type has great differences in appearance, shape, scale, texture, and other aspects. The quality, effectiveness, and practicality of WTBs2025 are verified from multiple perspectives, models, and scenes. Among them, YOLO26 [^30] is an object detection algorithm proposed by Ultralytics in January 2026. It features end-to-end NMS-free inference, efficient edge deployment, and strong multi-scale defect detection capability. The detection results of some one-stage and two-stage object detection models are shown in Table [6](https://www.nature.com/articles/s41597-026-07455-1#Tab6).

**Table 6 Test results of different models for various types of defects in WTBs2025.**

From Table [6](https://www.nature.com/articles/s41597-026-07455-1#Tab6), different models exhibit clear differences in detection performance across defect types. For protective film damage and paint crack, YOLO series models (YOLOv8, YOLOv9, YOLOv10, YOLO11, YOLO26) achieve higher mAP values than Faster R-CNN, SSD, and RetinaNet, reflecting their ability to accurately localize defects with distinct structural patterns. For coating detachment, which is smaller and less visually prominent, two-stage models such as Faster R-CNN and SSD show lower mAP, whereas YOLO11 and YOLO26 improve detection performance through enhanced feature aggregation.

For lightning strike, the YOLO series maintains high mAP and recall, while SSD and RetinaNet show a larger drop in performance. Similar trends are observed for erosion and pinhole defects, where detection performance varies according to defect size, shape, and texture complexity. YOLO11 and YOLO26 provide higher scores across both large and small defects, indicating that their multi-scale feature fusion contributes to better localization across diverse defect types.

Overall, the WTBs2025 dataset, with its variety of defect types, scales, and textures, allows for the evaluation of the strengths and limitations of different architectures. One-stage models provide consistently higher detection accuracy for visually distinct and multi-scale defects, while two-stage models perform comparatively lower for smaller or less prominent defects. This comparison demonstrates that the dataset can effectively benchmark models on different defect categories and scales.

### GA-DCGAN augmentation evaluation

To evaluate the effectiveness of GA-DCGAN in augmenting the lightning damage dataset, we conducted experiments based on the YOLO11 model, comparing two training settings:

1. the original training set containing only real samples (Original),
2. the augmented training set, including GA-DCGAN generated lightning damage samples (Augmented).

The detection performance of YOLO11 on lightning strike was evaluated before and after GA-DCGAN augmentation. The performance was measured using Precision (P), Recall (R), and mAP. As shown in Table [7](https://www.nature.com/articles/s41597-026-07455-1#Tab7), the model trained on the augmented dataset achieves substantial improvements over the model trained on the original dataset, with mAP increasing from 76.2% to 85.5%, Precision increasing from 81.4% to 91.1%, and Recall increasing from 71.5% to 80.3%. These results indicate that GA-DCGAN generated samples effectively mitigate the scarcity of lightning strike samples and significantly enhance YOLO11’s feature learning capability for this rare defect class.

**Table 7 Detection performance comparison between original and GA-DCGAN augmented training sets for lightning damage.**

### Visualization of defect detection results for different defect types

To provide a more intuitive understanding of the detection performance, qualitative visualization results of the defect detection model are presented. Representative detection examples for each defect type are illustrated to demonstrate the model’s ability to localize and recognize different wind turbine blade surface defects under diverse appearance characteristics. The visualization results are shown in Fig. [9](https://www.nature.com/articles/s41597-026-07455-1#Fig9).

**Fig. 9**

![Fig. 9](https://media.springernature.com/lw685/springer-static/image/art%3A10.1038%2Fs41597-026-07455-1/MediaObjects/41597_2026_7455_Fig9_HTML.png?as=webp)

[Full size image](https://www.nature.com/articles/s41597-026-07455-1/figures/9)

Visualized results.

As shown in the visualization results, the proposed detection model can accurately identify the defect regions and generate precise bounding boxes for various defect types. The predicted results show good alignment with the actual defect locations, indicating that the model effectively captures discriminative visual features such as shape, texture, and scale variations across different defect categories.

## Data availability

The self-constructed wind turbine blades surface defect dataset employed in this study has been deposited in the figshare repository and is publicly available at [https://doi.org/10.6084/m9.figshare.28876391](https://doi.org/10.6084/m9.figshare.28876391). Public access to the dataset is provided to support the transparency, reproducibility, and independent verification of the findings presented in this paper.

## Code availability

GA-DCGAN code is used in secondary data augmentation, and we publish and share the model code. ([https://github.com/ruihua333/GA-DCGAN](https://github.com/ruihua333/GA-DCGAN)).

## References

## Acknowledgements

This project is supported by the Shaanxi Provincial Key Research and Development Program. Project Name: Online Autonomous Inspection and Intelligent Damage Diagnosis of Wind Turbine Blades. Project No.: 2024GX-YBXM-523.

## Ethics declarations

### Competing interests

The authors declare that they have no known competing financial interests or personal relationships that could have appeared to influence the work reported in this paper.

## Additional information

**Publisher’s note** Springer Nature remains neutral with regard to jurisdictional claims in published maps and institutional affiliations.

## Rights and permissions

**Open Access** This article is licensed under a Creative Commons Attribution-NonCommercial-NoDerivatives 4.0 International License, which permits any non-commercial use, sharing, distribution and reproduction in any medium or format, as long as you give appropriate credit to the original author(s) and the source, provide a link to the Creative Commons licence, and indicate if you modified the licensed material. You do not have permission under this licence to share adapted material derived from this article or parts of it. The images or other third party material in this article are included in the article’s Creative Commons licence, unless indicated otherwise in a credit line to the material. If material is not included in the article’s Creative Commons licence and your intended use is not permitted by statutory regulation or exceeds the permitted use, you will need to obtain permission directly from the copyright holder. To view a copy of this licence, visit [http://creativecommons.org/licenses/by-nc-nd/4.0/](http://creativecommons.org/licenses/by-nc-nd/4.0/).

[^1]: Pan, X. *et al*. Wind turbine blade fault detection based on graph Fourier transform and deep learning. *Digital Signal Processing* **159**, 105007 (2025).

[Article](https://doi.org/10.1016%2Fj.dsp.2025.105007) [Google Scholar](http://scholar.google.com/scholar_lookup?&title=Wind%20turbine%20blade%20fault%20detection%20based%20on%20graph%20Fourier%20transform%20and%20deep%20learning&journal=Digital%20Signal%20Processing&doi=10.1016%2Fj.dsp.2025.105007&volume=159&publication_year=2025&author=Pan%2CX)

[^2]: Gohar, I., Yew, W. K., Halimi, A. & See, J. Review of state-of-the-art surface defect detection on wind turbine blades through aerial imagery: Challenges and recommendations. *Engineering Applications of Artificial Intelligence* **144**, 109970 (2025).

[Article](https://doi.org/10.1016%2Fj.engappai.2024.109970) [Google Scholar](http://scholar.google.com/scholar_lookup?&title=Review%20of%20state-of-the-art%20surface%20defect%20detection%20on%20wind%20turbine%20blades%20through%20aerial%20imagery%3A%20Challenges%20and%20recommendations&journal=Engineering%20Applications%20of%20Artificial%20Intelligence&doi=10.1016%2Fj.engappai.2024.109970&volume=144&publication_year=2025&author=Gohar%2CI&author=Yew%2CWK&author=Halimi%2CA&author=See%2CJ)

[^3]: Li, W., Zhao, W. & Du, Y. Large-scale wind turbine blade operational condition monitoring based on UAV and improved YOLOv5 deep learning model. *Mechanical Systems and Signal Processing* **226**, 112386 (2025).

[Article](https://doi.org/10.1016%2Fj.ymssp.2025.112386) [Google Scholar](http://scholar.google.com/scholar_lookup?&title=Large-scale%20wind%20turbine%20blade%20operational%20condition%20monitoring%20based%20on%20UAV%20and%20improved%20YOLOv5%20deep%20learning%20model&journal=Mechanical%20Systems%20and%20Signal%20Processing&doi=10.1016%2Fj.ymssp.2025.112386&volume=226&publication_year=2025&author=Li%2CW&author=Zhao%2CW&author=Du%2CY)

[^4]: Zou, L., Chen, A., Yang, X. & Sun, Y. An improved method of AUD-YOLO for surface damage detection of wind turbine blades. *Scientific Reports* **15**, 5833 (2025).

[Article](https://doi.org/10.1038%2Fs41598-025-89864-7) [ADS](http://adsabs.harvard.edu/cgi-bin/nph-data_query?link_type=ABSTRACT&bibcode=2025NatSR..15.5833Z) [CAS](https://www.nature.com/articles/cas-redirect/1:CAS:528:DC%2BB2MXksFSguro%3D) [PubMed](http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?cmd=Retrieve&db=PubMed&dopt=Abstract&list_uids=39966521) [PubMed Central](http://www.ncbi.nlm.nih.gov/pmc/articles/PMC11836457) [Google Scholar](http://scholar.google.com/scholar_lookup?&title=An%20improved%20method%20of%20AUD-YOLO%20for%20surface%20damage%20detection%20of%20wind%20turbine%20blades&journal=Scientific%20Reports&doi=10.1038%2Fs41598-025-89864-7&volume=15&publication_year=2025&author=Zou%2CL&author=Chen%2CA&author=Yang%2CX&author=Sun%2CY)

[^5]: Heo, S.-J. & Na, W. S. Review of Drone-Based Technologies for Wind Turbine Blade Inspection. *Electronics* **14**, 227 (2025).

[Article](https://doi.org/10.3390%2Felectronics14020227) [Google Scholar](http://scholar.google.com/scholar_lookup?&title=Review%20of%20Drone-Based%20Technologies%20for%20Wind%20Turbine%20Blade%20Inspection&journal=Electronics&doi=10.3390%2Felectronics14020227&volume=14&publication_year=2025&author=Heo%2CS-J&author=Na%2CWS)

[^6]: Du, Y. *et al*. Damage detection techniques for wind turbine blades: A review. *Mechanical Systems and Signal Processing* **141**, 106445 (2020).

[Article](https://doi.org/10.1016%2Fj.ymssp.2019.106445) [Google Scholar](http://scholar.google.com/scholar_lookup?&title=Damage%20detection%20techniques%20for%20wind%20turbine%20blades%3A%20A%20review&journal=Mechanical%20Systems%20and%20Signal%20Processing&doi=10.1016%2Fj.ymssp.2019.106445&volume=141&publication_year=2020&author=Du%2CY)

[^7]: Ren, Z., Verma, A. S., Li, Y., Teuwen, J. J. E. & Jiang, Z. Offshore wind turbine operations and maintenance: A state-of-the-art review. *Renewable and Sustainable Energy Reviews* **144**, 110886 (2021).

[Article](https://doi.org/10.1016%2Fj.rser.2021.110886) [Google Scholar](http://scholar.google.com/scholar_lookup?&title=Offshore%20wind%20turbine%20operations%20and%20maintenance%3A%20A%20state-of-the-art%20review&journal=Renewable%20and%20Sustainable%20Energy%20Reviews&doi=10.1016%2Fj.rser.2021.110886&volume=144&publication_year=2021&author=Ren%2CZ&author=Verma%2CAS&author=Li%2CY&author=Teuwen%2CJJE&author=Jiang%2CZ)

[^8]: Deng, L., Guo, Y. & Chai, B. Defect Detection on a Wind Turbine Blade Based on Digital Image Processing. *Processes* **9**, 1452 (2021).

[Article](https://doi.org/10.3390%2Fpr9081452) [Google Scholar](http://scholar.google.com/scholar_lookup?&title=Defect%20Detection%20on%20a%20Wind%20Turbine%20Blade%20Based%20on%20Digital%20Image%20Processing&journal=Processes&doi=10.3390%2Fpr9081452&volume=9&publication_year=2021&author=Deng%2CL&author=Guo%2CY&author=Chai%2CB)

[^9]: Tiwari, K. A. & Raisutis, R. Post-processing of ultrasonic signals for the analysis of defects in wind turbine blade using guided waves. *The Journal of Strain Analysis for Engineering Design* **53**, 546–555 (2018).

[Article](https://doi.org/10.1177%2F0309324718772668) [Google Scholar](http://scholar.google.com/scholar_lookup?&title=Post-processing%20of%20ultrasonic%20signals%20for%20the%20analysis%20of%20defects%20in%20wind%20turbine%20blade%20using%20guided%20waves&journal=The%20Journal%20of%20Strain%20Analysis%20for%20Engineering%20Design&doi=10.1177%2F0309324718772668&volume=53&pages=546-555&publication_year=2018&author=Tiwari%2CKA&author=Raisutis%2CR)

[^10]: Tang, J., Soua, S., Mares, C. & Gan, T.-H. An experimental study of acoustic emission methodology for in service condition monitoring of wind turbine blades. *Renewable Energy* **99**, 170–179 (2016).

[Article](https://doi.org/10.1016%2Fj.renene.2016.06.048) [Google Scholar](http://scholar.google.com/scholar_lookup?&title=An%20experimental%20study%20of%20acoustic%20emission%20methodology%20for%20in%20service%20condition%20monitoring%20of%20wind%20turbine%20blades&journal=Renewable%20Energy&doi=10.1016%2Fj.renene.2016.06.048&volume=99&pages=170-179&publication_year=2016&author=Tang%2CJ&author=Soua%2CS&author=Mares%2CC&author=Gan%2CT-H)

[^11]: Liu Q., L. Y., Zhang J., Ai Z., Cheng Q., Yang S. Research on surface crack identification method of large wind turbine blade based on WPT-SVD-KELM. Acta Energiae Solaris Sinica. 44(3), 155-161 (2023).

[^12]: Li, M., DAI, J. & CHEN, H. Research on strain sensing transmission characteristics of wind turbine blades based on optical fiber sensing. *Acta energiae solaris sinica* **43** (7), 375–384 (2025).

[Google Scholar](http://scholar.google.com/scholar_lookup?&title=Research%20on%20strain%20sensing%20transmission%20characteristics%20of%20wind%20turbine%20blades%20based%20on%20optical%20fiber%20sensing&journal=Acta%20energiae%20solaris%20sinica&volume=43&issue=7&pages=375-384&publication_year=2025&author=Li%2CM&author=DAI%2CJ&author=CHEN%2CH)

[^13]: Gardner, P. *et al*. Overcoming the problem of repair instructural health monitoring: Metric-informed transfer learning. *Journal of Sound and Vibration* **510**, 116245 (2021).

[Article](https://doi.org/10.1016%2Fj.jsv.2021.116245) [Google Scholar](http://scholar.google.com/scholar_lookup?&title=Overcoming%20the%20problem%20of%20repair%20instructural%20health%20monitoring%3A%20Metric-informed%20transfer%20learning&journal=Journal%20of%20Sound%20and%20Vibration&doi=10.1016%2Fj.jsv.2021.116245&volume=510&publication_year=2021&author=Gardner%2CP)

[^14]: Erazo, K. *et al*. Vibration-based structural health monitoring under changing environmental conditions using Kalman filtering. *Mechanical Systems and Signal Processing* **117**, 1–15 (2019).

[Article](https://doi.org/10.1016%2Fj.ymssp.2018.07.041) [ADS](http://adsabs.harvard.edu/cgi-bin/nph-data_query?link_type=ABSTRACT&bibcode=2019MSSP..117....1E) [Google Scholar](http://scholar.google.com/scholar_lookup?&title=Vibration-based%20structural%20health%20monitoring%20under%20changing%20environmental%20conditions%20using%20Kalman%20filtering&journal=Mechanical%20Systems%20and%20Signal%20Processing&doi=10.1016%2Fj.ymssp.2018.07.041&volume=117&pages=1-15&publication_year=2019&author=Erazo%2CK)

[^15]: Friedmann, A. *et al*. Wind turbine condition monitoring dataset of Fraunhofer LBF. *Scientific data* **11**, 1–12 (2024).

[Google Scholar](http://scholar.google.com/scholar_lookup?&title=Wind%20turbine%20condition%20monitoring%20dataset%20of%20Fraunhofer%20LBF&journal=Scientific%20data&volume=11&pages=1-12&publication_year=2024&author=Friedmann%2CA)

[^16]: Yang, X., Zhang, Y., Lv, W. & Wang, D. Image recognition of wind turbine blade damage based on a deep learning model with transfer learning and an ensemble learning classifier. *Renewable Energy* **163**, 386–397 (2021).

[Article](https://doi.org/10.1016%2Fj.renene.2020.08.125) [Google Scholar](http://scholar.google.com/scholar_lookup?&title=Image%20recognition%20of%20wind%20turbine%20blade%20damage%20based%20on%20a%20deep%20learning%20model%20with%20transfer%20learning%20and%20an%20ensemble%20learning%20classifier&journal=Renewable%20Energy&doi=10.1016%2Fj.renene.2020.08.125&volume=163&pages=386-397&publication_year=2021&author=Yang%2CX&author=Zhang%2CY&author=Lv%2CW&author=Wang%2CD)

[^17]: Zhang, S. *et al*. UAV based defect detection and fault diagnosis for static and rotating wind turbine blade: a review. *Nondestructive Testing and Evaluation* **40**, 1691–1729 (2025).

[Article](https://doi.org/10.1080%2F10589759.2024.2395363) [ADS](http://adsabs.harvard.edu/cgi-bin/nph-data_query?link_type=ABSTRACT&bibcode=2025NTE....40.1691Z) [Google Scholar](http://scholar.google.com/scholar_lookup?&title=UAV%20based%20defect%20detection%20and%20fault%20diagnosis%20for%20static%20and%20rotating%20wind%20turbine%20blade%3A%20a%20review&journal=Nondestructive%20Testing%20and%20Evaluation&doi=10.1080%2F10589759.2024.2395363&volume=40&pages=1691-1729&publication_year=2025&author=Zhang%2CS)

[^18]: Wang, L. & Zhang, Z. Automatic Detection of Wind Turbine Blade Surface Cracks Based on UAV-Taken Images. *IEEE Transactions on Industrial Electronics* **64**, 7293–7303 (2017).

[Article](https://doi.org/10.1109%2FTIE.2017.2682037) [ADS](http://adsabs.harvard.edu/cgi-bin/nph-data_query?link_type=ABSTRACT&bibcode=2017ITIE...64.7293W) [Google Scholar](http://scholar.google.com/scholar_lookup?&title=Automatic%20Detection%20of%20Wind%20Turbine%20Blade%20Surface%20Cracks%20Based%20on%20UAV-Taken%20Images&journal=IEEE%20Transactions%20on%20Industrial%20Electronics&doi=10.1109%2FTIE.2017.2682037&volume=64&pages=7293-7303&publication_year=2017&author=Wang%2CL&author=Zhang%2CZ)

[^19]: Davis, M., Nazario Dejesus, E., Shekaramiz, M., Zander, J. & Memari, M. Identification and Localization of Wind Turbine Blade Faults Using Deep Learning. *Applied Sciences* **14**, 6319 (2024).

[Article](https://doi.org/10.3390%2Fapp14146319) [CAS](https://www.nature.com/articles/cas-redirect/1:CAS:528:DC%2BB2cXhvVOrsbvI) [Google Scholar](http://scholar.google.com/scholar_lookup?&title=Identification%20and%20Localization%20of%20Wind%20Turbine%20Blade%20Faults%20Using%20Deep%20Learning&journal=Applied%20Sciences&doi=10.3390%2Fapp14146319&volume=14&publication_year=2024&author=Davis%2CM&author=Nazario%20Dejesus%2CE&author=Shekaramiz%2CM&author=Zander%2CJ&author=Memari%2CM)

[^20]: Shihavuddin, A. S. M. *et al*. Wind Turbine Surface Damage Detection by Deep Learning Aided Drone Inspection Analysis. *Energies* **12**, 676 (2019).

[Article](https://doi.org/10.3390%2Fen12040676) [Google Scholar](http://scholar.google.com/scholar_lookup?&title=Wind%20Turbine%20Surface%20Damage%20Detection%20by%20Deep%20Learning%20Aided%20Drone%20Inspection%20Analysis&journal=Energies&doi=10.3390%2Fen12040676&volume=12&publication_year=2019&author=Shihavuddin%2CASM)

[^21]: Zhu, X. *et al*. Damage identification of wind turbine blades based on deep learning and ultrasonic testing. *Nondestructive Testing and Evaluation* **40**, 508–533 (2025).

[Article](https://doi.org/10.1080%2F10589759.2024.2324373) [ADS](http://adsabs.harvard.edu/cgi-bin/nph-data_query?link_type=ABSTRACT&bibcode=2025NTE....40..508Z) [Google Scholar](http://scholar.google.com/scholar_lookup?&title=Damage%20identification%20of%20wind%20turbine%20blades%20based%20on%20deep%20learning%20and%20ultrasonic%20testing&journal=Nondestructive%20Testing%20and%20Evaluation&doi=10.1080%2F10589759.2024.2324373&volume=40&pages=508-533&publication_year=2025&author=Zhu%2CX)

[^22]: Radford A, M. L., Chintala S. Unsupervised Representation Learning with Deep Convolutional Generative Adversarial Networks. Computer ence. arXiv preprint arXiv:1511, 06434 (2015).

[^23]: Korhonen, J. & You, J. Peak signal-to-noise ratio revisited: is simple beautiful? Proceedings of the International Workshop on Quality of Multimedia Experience. 37–38 (2012).

[^24]: Wang, Z. *et al*. Image quality assessment: from error visibility to structural similarity. *IEEE Transactions on Image Processing* **13** (4), 600–612 (2004).

[Article](https://doi.org/10.1109%2FTIP.2003.819861) [ADS](http://adsabs.harvard.edu/cgi-bin/nph-data_query?link_type=ABSTRACT&bibcode=2004ITIP...13..600W) [PubMed](http://www.ncbi.nlm.nih.gov/entrez/query.fcgi?cmd=Retrieve&db=PubMed&dopt=Abstract&list_uids=15376593) [Google Scholar](http://scholar.google.com/scholar_lookup?&title=Image%20quality%20assessment%3A%20from%20error%20visibility%20to%20structural%20similarity&journal=IEEE%20Transactions%20on%20Image%20Processing&doi=10.1109%2FTIP.2003.819861&volume=13&issue=4&pages=600-612&publication_year=2004&author=Wang%2CZ)

[^25]: Zhang, R. *et al*. The unreasonable effectiveness of deep features as a perceptual metric. *Proceedings of the IEEE Conference on Computer Vision and Pattern Recognition*. 586–595 (2018).

[^26]: Zhang, R. H. *et al*. WTBs2025: wind turbine blades surface defect high-quality image dataset construction and performance validation. *figshare* [https://doi.org/10.6084/m9.figshare.28876391](https://doi.org/10.6084/m9.figshare.28876391) (2025).

[^27]: Redmon, J., Divvala, S., Girshick, R. & Farhadi, A. You Only Look Once: Unified, Real-Time Object Detection. *Computer Vision & Pattern Recognition*, (2016).

[^28]: Liu, W. *et al*. SSD: Single Shot MultiBox Detector. *ECCV* **2016**, 21–37 (2016).

[Google Scholar](http://scholar.google.com/scholar_lookup?&title=SSD%3A%20Single%20Shot%20MultiBox%20Detector&journal=ECCV&volume=2016&pages=21-37&publication_year=2016&author=Liu%2CW)

[^29]: Girshick, R., Donahue, J., Darrell, T. & Malik, J. Rich feature hierarchies for accurate object detection and semantic segmentation. *Proceedings of the IEEE Conference on Computer Vision and Pattern Recognition*. 580–587 (2014).

[^30]: Sapkota, R. *et al*. YOLO26: key architectural enhancements and performance benchmarking for real-time object detection. arXiv:2509.25164 (2025).