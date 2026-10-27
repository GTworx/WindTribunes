---
title: "Failure classification of wind turbine operational conditions using hybrid machine learning"
source: "https://wes.copernicus.org/articles/11/1057/2026/"
author:
  - "[[Marcela Rodrigues Machado]]"
  - "[[Amanda Aryda Silva Rodrigues de Sousa]]"
  - "[[Jefferson da Silva Coelho]]"
  - "[[Rafael de Oliveira Teloli]]"
published:
created: 2026-10-25
description: "Abstract. Wind turbines are complex electromechanical systems that require continuous monitoring to ensure operational efficiency, reduce maintenance costs, and prevent critical failures. Machine learning has shown great promise in structural health monitoring (SHM) by enabling automated fault detection through data-driven approaches. However, challenges remain in adapting SHM methods to complex environmental conditions while maintaining reliable fault detection and classification. This work proposes a hybrid model that combines supervised and unsupervised learning techniques for classifying operational failures in wind turbines. The proposed framework integrates multimodal data, combining structural and environmental information to monitor four distinct operational states. The approach begins with analysing sensor signals and extracting descriptive features that capture the turbine's dynamic behaviour, accounting for the effects of temperature and wind speed. The unsupervised k-means is applied to label and cluster the dataset, while feature and sensor selection are performed using canonical correlation analysis to rank the most informative variables. A novel relative change damage index is introduced to normalize and scale features based on their relative variability, enhancing the accuracy of clustering and fault classification. Classification is performed using six machine learning algorithms, and the best model is identified. Experimental results, also considering environmental conditions and sensor failures, demonstrate strong performance across both binary and multi-class tasks, including the detection of pitch drive faults and the accurate identification of rotor icing and aerodynamic imbalance. The model achieved classification accuracies ranging from 85 % to 98 %, highlighting its effectiveness in diagnosing wind turbine conditions, and improving the overall reliability and operational analysis of these systems."
tags:
  - "clippings"
---
[Articles](https://wes.copernicus.org/) | [Volume 11, issue 3](https://wes.copernicus.org/articles/11/issue3.html)

https://doi.org/10.5194/wes-11-1057-2026

© Author(s) 2026. This work is distributed under  
the Creative Commons Attribution 4.0 License.

https://doi.org/10.5194/wes-11-1057-2026

© Author(s) 2026. This work is distributed under  
the Creative Commons Attribution 4.0 License.

Marcela Rodrigues Machado, Amanda Aryda Silva Rodrigues de Sousa, Jefferson da Silva Coelho, and Rafael de Oliveira Teloli

Wind turbines are complex electromechanical systems that require continuous monitoring to ensure operational efficiency, reduce maintenance costs, and prevent critical failures. Machine learning has shown great promise in structural health monitoring (SHM) by enabling automated fault detection through data-driven approaches. However, challenges remain in adapting SHM methods to complex environmental conditions while maintaining reliable fault detection and classification. This work proposes a hybrid model that combines supervised and unsupervised learning techniques for classifying operational failures in wind turbines. The proposed framework integrates multimodal data, combining structural and environmental information to monitor four distinct operational states. The approach begins with analysing sensor signals and extracting descriptive features that capture the turbine's dynamic behaviour, accounting for the effects of temperature and wind speed. The unsupervised *k* -means is applied to label and cluster the dataset, while feature and sensor selection are performed using canonical correlation analysis to rank the most informative variables. A novel relative change damage index is introduced to normalize and scale features based on their relative variability, enhancing the accuracy of clustering and fault classification. Classification is performed using six machine learning algorithms, and the best model is identified. Experimental results, also considering environmental conditions and sensor failures, demonstrate strong performance across both binary and multi-class tasks, including the detection of pitch drive faults and the accurate identification of rotor icing and aerodynamic imbalance. The model achieved classification accuracies ranging from 85 % to 98 %, highlighting its effectiveness in diagnosing wind turbine conditions, and improving the overall reliability and operational analysis of these systems.

Wind turbines are complex electromechanical systems that operate in hazardous environments and contain critical components, including blades, main bearing, main shaft, gearbox, nacelle, tower, foundation, yaw system, and connecting bolts. Continuous monitoring of these components is essential to ensure their integrity, reduce costs, and enhance the operational efficiency of the turbines ([Veers et al.](https://wes.copernicus.org/articles/11/1057/2026/#bib1.bibx59), [^77]). Like any other electromechanical system, wind turbines are subject to several unforeseen and serious failures that can result in downtime ([Asian et al.](https://wes.copernicus.org/articles/11/1057/2026/#bib1.bibx8), [^28]; [Machado and Dutkiewicz](https://wes.copernicus.org/articles/11/1057/2026/#bib1.bibx43), [^61]; [Dutkiewicz and Machado](https://wes.copernicus.org/articles/11/1057/2026/#bib1.bibx20), [^39] [a](https://wes.copernicus.org/articles/11/1057/2026/#bib1.bibx20)). Mechanical, electrical, and environmental failures are the primary causes of issues in wind turbines ([Thomas](https://wes.copernicus.org/articles/11/1057/2026/#bib1.bibx57), [^75]). Mechanical failures typically affect components such as the rotor blades, gearbox, bearings, and main shaft, compromising the turbine's performance. In the electrical system, which includes generators, converters, and control systems, failures can result from insulation degradation, thermal voltages, and electrical transients, impacting the efficiency and safety of operation ([Liu et al.](https://wes.copernicus.org/articles/11/1057/2026/#bib1.bibx41), [^59]; [Dutkiewicz and Machado](https://wes.copernicus.org/articles/11/1057/2026/#bib1.bibx21), [^40] [b](https://wes.copernicus.org/articles/11/1057/2026/#bib1.bibx21), [c](https://wes.copernicus.org/articles/11/1057/2026/#bib1.bibx22)). Environmental factors, such as extreme temperatures, atmospheric discharges, humidity, wind direction and speed, and corrosion, pose significant challenges to turbine reliability and service life ([Figueiredo et al.](https://wes.copernicus.org/articles/11/1057/2026/#bib1.bibx26), [^44]; [Morozovska et al.](https://wes.copernicus.org/articles/11/1057/2026/#bib1.bibx46), [^64]). An effective wind turbine monitoring strategy combines the condition monitoring (CM) of mechanical subsystems and SHM of structural elements ([Civera and Surace](https://wes.copernicus.org/articles/11/1057/2026/#bib1.bibx14), [^34]). The authors highlight the growing integration of both into AI-based systems, aiming to improve reliability and operational safety. Research on the fault detection of turbine components using machine learning (ML) techniques has advanced significantly over the past decade. It has significantly enhanced the efficiency and accuracy of SHM techniques by automating data analysis and improving damage detection ([Smarsly et al.](https://wes.copernicus.org/articles/11/1057/2026/#bib1.bibx54), [^72]; [Flah et al.](https://wes.copernicus.org/articles/11/1057/2026/#bib1.bibx27), [^45]; [Farrar and Worden](https://wes.copernicus.org/articles/11/1057/2026/#bib1.bibx25), [^43]). These algorithms process large volumes of data, identifying patterns and anomalies that may indicate structural deterioration. Thus, structural health monitoring with machine learning (SHM-ML) has emerged as a powerful data-driven approach, enhancing multi-sensor systems and intelligent algorithms to detect, localize, and quantify structural damage under complex environmental and operational conditions.

Deep learning (DL) and machine learning (ML) models have emerged as leading approaches for wind turbine fault diagnosis, outperforming traditional methods in handling complex, nonlinear, and noisy operational data. Their applications span vision-based approaches ([Li et al.](https://wes.copernicus.org/articles/11/1057/2026/#bib1.bibx39), [^57]; [Dwivedi et al.](https://wes.copernicus.org/articles/11/1057/2026/#bib1.bibx23), [^41]; [Li et al.](https://wes.copernicus.org/articles/11/1057/2026/#bib1.bibx40), [^58]; [Zhao et al.](https://wes.copernicus.org/articles/11/1057/2026/#bib1.bibx66), [^84]), acoustic-based techniques ([Regan et al.](https://wes.copernicus.org/articles/11/1057/2026/#bib1.bibx51), [^69]; [Kuo et al.](https://wes.copernicus.org/articles/11/1057/2026/#bib1.bibx36), [^54]; [Lei et al.](https://wes.copernicus.org/articles/11/1057/2026/#bib1.bibx37), [^55]; [Carmona-Troyo et al.](https://wes.copernicus.org/articles/11/1057/2026/#bib1.bibx12), [^32]), and vibration-based monitoring, among others. Vision-based methods, however, remain limited to identifying superficial or external damage, and are strongly affected by lighting and weather conditions, while being unable to detect subsurface faults. Acoustic techniques are highly sensitive to environmental noise and often require expensive sensor maintenance, adding complexity to the monitoring process. Vibration-based monitoring is among the most established SHM strategies, as variations in natural frequencies, mode shapes, and damping ratios are closely associated with structural degradation. Nevertheless, its effectiveness can be reduced by operational variability, which makes it more difficult to detect early-stage or localized damage. Despite these limitations, vibration monitoring remains a widely applied technique for various wind turbine components.

Hybrid approaches involve strategies that combine multiple machine learning models, integrate multimodal or heterogeneous data, or fuse complementary algorithms with multiphysics information, thereby enhancing model generalization, interpretability, and reliability in complex monitoring scenarios. In this context, [Baquerizo et al.](https://wes.copernicus.org/articles/11/1057/2026/#bib1.bibx9) ([^29]) proposed a Siamese neural network using image-like matrices from 24-channel triaxial accelerometer data for jacket structures, achieving 100 % accuracy in crack and bolt looseness detection. Building on this, [Antoniadou et al.](https://wes.copernicus.org/articles/11/1057/2026/#bib1.bibx5) ([^26] [b](https://wes.copernicus.org/articles/11/1057/2026/#bib1.bibx5)) combined vibration analysis, SCADA, and ML algorithms (SVM, neural networks, Gaussian processes) for blade and gearbox monitoring, extracting features from time, frequency, and time-frequency domains using diverse sensors, including accelerometers, fibre optics, and thermography. Hybrid intelligent models for floating offshore turbines using a conventional neural network long short-term memory with attention mechanism (CNN-LSTM-ATT) with Chebyshev decomposition to forecast mooring-line tension under harsh seas were proposed in ([Tang et al.](https://wes.copernicus.org/articles/11/1057/2026/#bib1.bibx56), [^74]). This is a Gaussian process system for predicting crack location, severity, and remaining useful life composite blades in [Krishna et al.](https://wes.copernicus.org/articles/11/1057/2026/#bib1.bibx34) ([^52]); and a transformer-based PatchTST virtual sensor, trained on Alpha Ventus data, that accurately reconstructs strain in jacket foundations ([Ángel Encalada-Dávila et al.](https://wes.copernicus.org/articles/11/1057/2026/#bib1.bibx2), [^23]). A digital twin for mooring-line monitoring ([Mousavi et al.](https://wes.copernicus.org/articles/11/1057/2026/#bib1.bibx47), [^65]) used a hybrid CNN-LSTM with CEEMD/FDD-derived natural frequencies, achieving 97.65 % accuracy in damage localization and severity classification, outperforming the deep convolution neural network (DCNN), backpropagation neural network (BPNN), and support vector machine (SVM) under noise and environmental variability.

Wind turbine blade monitoring has increasingly leveraged hybrid machine learning models. Early approaches combined neural networks and Gaussian processes using frequency response functions and SCADA data ([Antoniadou et al.](https://wes.copernicus.org/articles/11/1057/2026/#bib1.bibx3), [^24], [^25] [a](https://wes.copernicus.org/articles/11/1057/2026/#bib1.bibx4)), while [Dervilis et al.](https://wes.copernicus.org/articles/11/1057/2026/#bib1.bibx18) ([^37] [b](https://wes.copernicus.org/articles/11/1057/2026/#bib1.bibx18), [a](https://wes.copernicus.org/articles/11/1057/2026/#bib1.bibx17)) employed auto-associative neural networks with RBF models to achieve high sensitivity with few false positives. Rule-based and ensemble methods ([Joshuva and Sugumaran](https://wes.copernicus.org/articles/11/1057/2026/#bib1.bibx30), [^48]; [Joshuva et al.](https://wes.copernicus.org/articles/11/1057/2026/#bib1.bibx31), [^49]), which integrated MLPs and logistic model trees with ARMA features, achieved 94.75 % accuracy in crack localization. More recent studies focus on hybrid architectures that fuse different algorithms or modalities. [Tsiapoki et al.](https://wes.copernicus.org/articles/11/1057/2026/#bib1.bibx58) ([^76]) combined environmental and operational effects with unsupervised clustering, [Movsessian et al.](https://wes.copernicus.org/articles/11/1057/2026/#bib1.bibx48) ([^66]) integrated Mahalanobis distance, XGBoost, and SHAP for explainable SHM, [Song et al.](https://wes.copernicus.org/articles/11/1057/2026/#bib1.bibx55) ([^73]) and [Sharma and Nava](https://wes.copernicus.org/articles/11/1057/2026/#bib1.bibx53) ([^71]) employed CNN-GRU and AR-CNN hybrids for offshore blade and mooring system monitoring (with over 93 % accuracy), and [Ashkarkalaei et al.](https://wes.copernicus.org/articles/11/1057/2026/#bib1.bibx6) ([^27] [a](https://wes.copernicus.org/articles/11/1057/2026/#bib1.bibx6), [b](https://wes.copernicus.org/articles/11/1057/2026/#bib1.bibx7)) combined one-class SVM, autoencoders, and DSFs with ANOVA-selected features with random forest (achieving F1 >95 %). Bayesian-optimized kNN/SVM frameworks ([Korolis et al.](https://wes.copernicus.org/articles/11/1057/2026/#bib1.bibx33), [^51]) and relevance vector machines ([Kuai et al.](https://wes.copernicus.org/articles/11/1057/2026/#bib1.bibx35), [^53]) further demonstrate the advantages of hybrid and sparse models, offering high accuracy and computational efficiency under environmental variability.

The vulnerability of towers and foundations has driven the development of hybrid ML-based SHM strategies. [Nguyen et al.](https://wes.copernicus.org/articles/11/1057/2026/#bib1.bibx49) ([^67]) combined artificial neural networks (ANNs) with modal parameters, such as mode shapes and frequencies, to localize and quantify tower damage in simulations. An extension proposed in [Hoxha et al.](https://wes.copernicus.org/articles/11/1057/2026/#bib1.bibx29) ([^47]) integrated vibration responses with multiple classifiers, including kNN, quadratic SVM, and Gaussian SVM, for tower fault detection. For jacket-type foundations, [Vidal et al.](https://wes.copernicus.org/articles/11/1057/2026/#bib1.bibx60) ([^78]) and [Leon-Medina et al.](https://wes.copernicus.org/articles/11/1057/2026/#bib1.bibx38) ([^56]) employed PCA for dimensionality reduction combined with classifiers such as kNN, SVM, and XGBoost to detect and localize cracks. [Ren and Yong](https://wes.copernicus.org/articles/11/1057/2026/#bib1.bibx52) ([^70]) advanced unsupervised hybrid methods using dynamically weighted *k* -means clustering to categorize tower fault types. Random forest classifiers can effectively monitor blade pitch misalignment, capturing subtle deviations ([Milani et al.](https://wes.copernicus.org/articles/11/1057/2026/#bib1.bibx45), [^63]). ANNs and Gaussian processes combined with SVM were used in drivetrain monitoring ([Elforjani](https://wes.copernicus.org/articles/11/1057/2026/#bib1.bibx24), [^42]), and feature extraction and PCA can enhance gearbox fault detection. [Zarrin et al.](https://wes.copernicus.org/articles/11/1057/2026/#bib1.bibx64) ([^82]) developed a neuromorphic model for classifying accelerometer data from healthy and damaged gearboxes, while [Gao et al.](https://wes.copernicus.org/articles/11/1057/2026/#bib1.bibx28) ([^46]) applied CNNs for bearing and gearbox fault detection. [Praveen et al.](https://wes.copernicus.org/articles/11/1057/2026/#bib1.bibx50) ([^68]) improved vibration monitoring by segmenting gearbox signals and validating them with decision trees, SVM, and deep neural networks. For bearing faults, [Vives](https://wes.copernicus.org/articles/11/1057/2026/#bib1.bibx61) ([^79]); [Vives et al.](https://wes.copernicus.org/articles/11/1057/2026/#bib1.bibx62) ([^80]) demonstrated the effectiveness of combining kNN, SVM, and deep learning, whereas [Meyer](https://wes.copernicus.org/articles/11/1057/2026/#bib1.bibx44) ([^62]) and [Amin et al.](https://wes.copernicus.org/articles/11/1057/2026/#bib1.bibx1) ([^22]) employed unsupervised and cyclostationary-feature CNNs for accurate health state classification. These studies highlight the advantages of hybrid approaches that integrate multiple algorithms and preprocessing techniques to enhance robustness in fault detection and classification.

Data quality, imbalance, generalization, feature selection, and explainability remain challenges in wind turbine monitoring, with ongoing research focused on improving applicability, addressing data limitations, and enhancing interpretability. Despite recent advances, SHM techniques still face difficulties in generalizing across operational and environmental conditions while ensuring reliable detection. While many studies employ supervised, unsupervised, or hybrid learning for anomaly detection and classification, these methods are still limited to specific operations and the detection of local component faults. Hybrid machine learning models, particularly those that account for environmental variability, have strong potential for wind turbine diagnostics, enabling accurate early fault detection and adaptability. However, a research gap remains in designing hybrid frameworks that balance computational efficiency and interpretability without compromising diagnostic performance.

This study proposes a hybrid monitoring that integrates multiple machine learning models with multimodal data to enhance the reliability, accuracy, and interpretability of fault detection in the Aventa wind turbine. Unlike conventional single-model or single-source approaches, the proposed framework effectively captures cross-domain correlations and accounts for environmental variability, enabling dependable monitoring under complex operational conditions. The methodology employs unsupervised *k* -means clustering to partition the data into homogeneous clusters, thereby facilitating pattern recognition without predefined labels. These clusters are subsequently analysed using multiple supervised machine learning algorithms for binary and multi-class fault classification, based on structural-temporal response signals and SCADA data (wind speed and temperature) from the Aventa onshore wind turbine. The framework simultaneously performs fault classification, feature ranking, and sensor selection, demonstrating flexibility in handling diverse input features and reinforcing SHM decision-making. The main contributions of this study are (i) the development of a hybrid ML framework for operational fault assessment combining multiple supervised and unsupervised learning techniques and multimodal data, (ii) the formulation of a feature relative change damage index strategy for feature normalization and scaling, and (iii) the implementation of a canonical correlation-based feature and sensor selection process. By integrating multiphysics information, the proposed model enhances diagnostic capability, computational efficiency, and prediction accuracy. Experimental validation on the Aventa 6.7 kW onshore wind turbine confirms high performance in both binary and multi-class fault classification. Six ML algorithms were compared, and the best-performing model achieved classification accuracies of 85 %–98 %. The framework reliably detected pitch drive faults, and accurately identified rotor icing and aerodynamic imbalance, even under varying environmental conditions and sensor failure scenarios, demonstrating its effectiveness and potential for real-world SHM applications.

The proposed monitoring model consists of seven steps, as illustrated in Fig. [^2], including (1) receiving the acquired data; (2) data processing and organization; (3) feature extraction, normalization, and grouping for similarity pattern; (4) unsupervised feature labelling and clustering; (5) feature and sensor selection; (6) data splitting, and ML failure identification and classification; and (7) fault classification and model evaluation. The final step also outputs the operational failure and identifies the best-performing ML algorithm based on its performance metric. The novelties of the presented study are associated with feature and sensor selection, data normalization, and multimodal and multiple fault classification, which are detailed in Sects. [2.2](https://wes.copernicus.org/articles/11/1057/2026/#Ch1.S2.SS2), [2.3](https://wes.copernicus.org/articles/11/1057/2026/#Ch1.S2.SS3), and [2.1](https://wes.copernicus.org/articles/11/1057/2026/#Ch1.S2.SS1). The pseudocode developed for the failure classification, presented in Algorithm [^1], has the following structure.

**Algorithm 1** Hybrid ML model for Aventa wind turbine failure classification.

1: **Data acquisition:** Receive time-domain structural response from accelerometer sensors and environmental conditions from the SCADA.

2: **Data processing:** Involves correcting raw data by checking for missing values and applying signal processing techniques.

3: **Feature extraction, normalization, and grouping:** Fifteen formulations are employed to extract features from the time-domain signal, which is then grouped by similarity (see Sect. [2.3](https://wes.copernicus.org/articles/11/1057/2026/#Ch1.S2.SS3)).

4: **Pattern recognition, labelling, and clustering:** Use the *k* -means unsupervised algorithm to cluster the data: $J = \sum_{i = 1}^{n} min_{k} \left(\left(x_{i} - \left(\overset{\overline}{x}\right)_{k}\right)^{2}\right)$

5: **Feature and sensor selection:** This is performed via canonical-correlation-based selection and final dataset organization.

6: **Data splitting and ML classification:** Split the dataset into training and testing as listed in Table [^10]. Further, apply the ML algorithms (SVM, K-NN, RF, NB, DT, and XGBoost) for failure identification and classification.

7: **Model evaluation:** Calculate the performance of the ML classifiers (Cross-validation, accuracy, precision, recall, and the F1-score), identification of the best ML model(s), and generation of the confusion matrix.

**Final decision:** This concerns information about failure state based on classification algorithm outcomes.

[![https://wes.copernicus.org/articles/11/1057/2026/wes-11-1057-2026-f01](https://wes.copernicus.org/articles/11/1057/2026/wes-11-1057-2026-f01-thumb.png)](https://wes.copernicus.org/articles/11/1057/2026/wes-11-1057-2026-f01-web.png)

**Figure 1** Pipeline of the hybrid machine learning model for fault classification on the Aventa 6.7 kW wind turbine.

[Download](https://wes.copernicus.org/articles/11/1057/2026/wes-11-1057-2026-f01.png)

## 2.1 Data processing, signal, and sensor analysis

The wind turbine monitored in this study is the Aventa AV-7 model, manufactured by Aventa AG (Switzerland) and commissioned by ETH. This turbine has a rated power of 6.7 kW and operates using a belt-driven generator coupled with a frequency converter and a variable-speed drive. It begins generating power at a wind speed of 2 m s <sup>−1</sup> and has a cut-off speed of 14 m s <sup>−1</sup>. The rotor has a diameter of 12.8 m with three blades and is mounted at a hub height of 18 m. The maximum rotational speed reaches 63 rpm. Turbine control is managed through a variable-speed and variable-pitch mechanism. The turbine is installed in Taggenberg, Switzerland (coordinates: 47°31 <sup>′</sup> 12.2 <sup>′′</sup>  N, 8°40 <sup>′</sup> 55.7 <sup>′′</sup>  E). Instrumentation and data acquisition were provided in [Chatzi et al.](https://wes.copernicus.org/articles/11/1057/2026/#bib1.bibx13) ([^33]) and include 14 accelerometers strategically placed along the tower, on the nacelle main frame, the main bearing, and the generator, as shown in Fig. [^3]. Additionally, two full-bridge strain gauges are mounted at the tower base to measure fore-aft and side-to-side strain, which can be converted into bending moments. Acceleration and strain signals are sampled at 200 Hz. Environmental measurements, including temperature and humidity, are collected at the tower base at a sampling rate of 1 Hz. Operational performance data (SCADA), including wind speed, nacelle yaw orientation, rotor RPM, power output, and turbine status, are recorded at 10 Hz. To ensure data quality and enhance the reliability of fault detection, a comprehensive supervised data preprocessing was implemented. This included supervised sensor analysis, outlier removal, signal segmentation, detrending, feature extraction, normalization, and similar feature identification and grouping.

[![https://wes.copernicus.org/articles/11/1057/2026/wes-11-1057-2026-f02](https://wes.copernicus.org/articles/11/1057/2026/wes-11-1057-2026-f02-thumb.png)](https://wes.copernicus.org/articles/11/1057/2026/wes-11-1057-2026-f02-web.png)

**Figure 2** Schematic representation of the turbine sensor channel and location ([Chatzi et al.](https://wes.copernicus.org/articles/11/1057/2026/#bib1.bibx13), [^33]). SCADA data and accelerometers marked in orange, blue, and yellow colours are adopted in the monitoring **(a)**. Temporal signal data of the turbine's NO and operation with failures **(b)**: top: sensor GEN NO-FC, NO-RI, and NO-AI placed from left to right, respectively; middle: sensor MSB NO-FC, NO-RI, and NO-AI; and bottom: sensor NMF NO-FC, NO-RI, and NO-AI.

[Download](https://wes.copernicus.org/articles/11/1057/2026/wes-11-1057-2026-f02.png)

**Table 1** Information on SCADA data and accelerometers used in the monitoring, with the respective sensor channel and location.

[![](https://wes.copernicus.org/articles/11/1057/2026/wes-11-1057-2026-t01-thumb.png)](https://wes.copernicus.org/articles/11/1057/2026/wes-11-1057-2026-t01.png)

[Download Print Version](https://wes.copernicus.org/articles/11/1057/2026/wes-11-1057-2026-t01.png) | [Download XLSX](https://wes.copernicus.org/articles/11/1057/2026/wes-11-1057-2026-t01.xlsx)

The data preprocessing stage begins by analysing the sensors' physics and evaluating each sensor's contribution to failure identification. The pre-established failures are the rotor icing event (RI), the flexible coupling of the linear drive of the collective pitch system (FC), and aerodynamic imbalance on one blade (AI). The Aventa dataset provides three-axis acceleration signals. Table [^4] lists the SCADA data and accelerometers used for monitoring, along with their respective sensor channels and locations. The *x* axis captures side-to-side turbine motion, and the *y* axis captures fore-aft turbine motion. Figure [^3] a illustrates the sensor locations within the turbine. Aside from the SCADA data (temperature and wind velocity), accelerometers marked in orange, blue, and yellow are used for monitoring. Specifically, three accelerometers are located in the nacelle, GEN *\_* ACC (orange), NMF *\_* ACC (blue), and MSB *\_* ACC (yellow); and one is located at the tower top, F5 *\_* ACC. The sensors record signals under the different operational conditions, including normal operation (NO). Figure [^3] also presents the raw temporal data available in the dataset. In the acceleration graphs, black lines indicate normal turbine operation, whereas coloured lines represent various failure conditions. To ensure consistent comparisons, all signals were selected from the same day, minimizing the influence of changing environmental conditions.

The top row of graphs shows the *x* axis response from the generator-mounted sensor (GEN), comparing NO with failures FC, RI, and AI, from left to right. The middle row displays the *x* axis response from the main shaft bearing sensor (MSB), and the bottom row shows the same for the nacelle main frame sensor (NMF), following the same failure comparison pattern. Both *x* and *y* axis signals were analysed, revealing consistent trends: FC failures led to a pronounced amplitude reduction, whereas RI and AI failures resulted in only minor amplitude changes. These variations may fluctuate daily due to environmental conditions. To ensure effective fault detection, data from accelerometer sensors placed at the tower top, nacelle, main shaft bearing, and generator were used in the model, considering their sensitivity to structural, mechanical, and aerodynamic failures.

## 2.2 Dataset

During data analysis, duplicate files were identified, prompting a data redistribution strategy to eliminate redundancies and streamline the process. The data were categorized and colour-coded by operational conditions and events, making patterns – such as seasonality, frequency, and duration – more apparent and visually accessible. These cleaning and reorganization steps ensure that the same data are not reused across different turbine operations, thereby reducing the risk of misclassification and misinterpretation during monitoring.

[![https://wes.copernicus.org/articles/11/1057/2026/wes-11-1057-2026-f03](https://wes.copernicus.org/articles/11/1057/2026/wes-11-1057-2026-f03-thumb.png)](https://wes.copernicus.org/articles/11/1057/2026/wes-11-1057-2026-f03-web.png)

**Figure 3** The feature dataset volume over the monitoring timeline categorized by yellow indicates RI, blue denotes NO, purple corresponds to AI, and orange represents the FC condition **(a)** (top). Wind speed boxplot **(a)** (middle), and mean temperature (**(a)** bottom). Boxplot of L05 sensor feature by wind speed variation **(b)** and feature by temperature variation **(c)**.

[Download](https://wes.copernicus.org/articles/11/1057/2026/wes-11-1057-2026-f03-high-res.png)

Feature extraction was performed after this reorganization. Aside from the accelerometer sensors, the supervisory control and data acquisition (SCADA) data include the temperature, wind speed, humidity, and power output. Temperature, wind speed, and acceleration responses are used for monitoring. Figure [^5] a shows the maximum values of the temporal spectrum for each operational condition mapped over the monitoring timeline. Each condition is colour-coded for clarity: yellow for RI, blue for NO, purple for AI, and orange for flexible FC. Events are plotted along the horizontal axis to highlight their temporal distribution. The timeline begins with a NO sample, followed by a pitch drive coupling failure recorded on 16 February 2022, which required replacement. From April to November 2022, the turbine operated normally, during which AI was intentionally simulated using roughness tape on the blades. Additionally, naturally occurring RI events were observed between December 2022 and February 2023. Wind speed fluctuates throughout the monitoring period, as indicated by the boxplot, which displays the minimum, maximum, median, and first and third quartiles of the wind speed data. Meanwhile, ambient temperature ranges from −2 to 26 °C throughout the year (see Fig. [^5] c).

Both environmental conditions – wind speed and temperature – significantly influence the dynamic response of the wind turbine over time. Figure [^5] b–c present boxplots showing the feature values corrected by wind speed and temperature, respectively. This analysis focuses on the RMS value of sensor NMF, selected for its highest-scoring features and well-defined failure patterns, which represent the general behaviour of the features. When correlating feature values with wind speed, the FC and AI conditions exhibit the greatest sensitivity to increasing wind speeds, though with relatively low dispersion. Conversely, RI, NO, and FC show higher maximum, minimum, and quartile values at lower wind speeds. Regarding temperature, rising temperatures primarily affect NO and AI conditions, whereas lower temperatures have a greater impact on FC and RI. These findings underscore the importance of incorporating environmental variables into the monitoring framework to improve the robustness and accuracy of fault classification. The SCADA data in the general dataset are considered the mean temperature and mean wind speed, both acquired over the 24 h of the respective day.

## 2.3 Feature extraction, normalization, and dataset organization

Feature selection involves choosing a subset of variables from the original dataset. This step transforms the spectrum data into new variables to create a refined dataset ([Bishop](https://wes.copernicus.org/articles/11/1057/2026/#bib1.bibx11), [^31]). Fifteen features are formulated using the time-domain signal ([Knittel et al.](https://wes.copernicus.org/articles/11/1057/2026/#bib1.bibx32), [^50]; [Barreto et al.](https://wes.copernicus.org/articles/11/1057/2026/#bib1.bibx10), [^30]; [Ashkarkalaei et al.](https://wes.copernicus.org/articles/11/1057/2026/#bib1.bibx6), [^27] [a](https://wes.copernicus.org/articles/11/1057/2026/#bib1.bibx6)), as presented in Table [^6], where *x* is the temporal spectrum signal and *p* is the sampling points value.

**Table 2** Temporal and statistical formulation used for feature extraction.

[![](https://wes.copernicus.org/articles/11/1057/2026/wes-11-1057-2026-t02-thumb.png)](https://wes.copernicus.org/articles/11/1057/2026/wes-11-1057-2026-t02.png)

[Download Print Version](https://wes.copernicus.org/articles/11/1057/2026/wes-11-1057-2026-t02.png) | [Download XLSX](https://wes.copernicus.org/articles/11/1057/2026/wes-11-1057-2026-t02.xlsx)

Temporal features are extracted from a signal's frequency or time content, such as maximum, minimum, amplitude range, energy, energy centre, skewness, signal rate, and RMS. It captures how the signal's energy is distributed over time. Statistical features, in turn, are computed from the signal's time-domain values, including the median, mean, variance, skewness, kurtosis, higher-order moments, and standard deviation, which characterize the overall distribution and variability of the signal. Together, these features are compiled, analysed, and evaluated for their similarity and sensitivity to the system's dynamic behaviour.

Despite feature refinement and grouping, the remaining features still pose a challenge due to their minimal amplitude variation, often differing by only a few digits. Such small variations can hinder accurate machine learning classification. To address this issue, the proposed relative change damage index incorporates a normalization step based on the relative change of each feature, defined as

$$
\begin{aligned}
(\text{1a}) \Delta_{f} = max \left(\mathbf{X}_{i}\right) - \mathbf{X}_{i} \\ (\text{1b}) \text{RC} = \frac{\Delta_{f}}{max \left(\Delta_{f}\right)} ,
\end{aligned}
$$

where **X** is a table containing the selected features and Δ <sub>f</sub> measures each feature's deviation from its maximum value within the selected feature set to each feature vector point (**X** <sub><i>i</i></sub>). The normalization factor RC rescales these deviations to the \[0, 1\] interval. This linear transformation preserves the original ordering and proportionality of the data, ensuring that the intrinsic dynamic pattern is maintained. At the same time, it amplifies subtle differences that would otherwise be masked by small numerical variations, thereby enhancing the sensitivity of the features for fault detection and classification. Hence, the RC normalization converts the data into dimensionless features that, prior to normalization, differed only slightly (e.g. 3.280 vs 3.286), rendering these differences numerically negligible for machine learning models. Thus, the proposed approach amplifies these small variations while preserving the intrinsic dynamic pattern. Features with values close to unity correspond to undamaged conditions, whereas values approaching zero indicate faults. Hence, the method enhances fault sensitivity and enables consistent comparison across features of different magnitudes, making the damage feature more sensitive to anomalies under varying operating states.

[![https://wes.copernicus.org/articles/11/1057/2026/wes-11-1057-2026-f04](https://wes.copernicus.org/articles/11/1057/2026/wes-11-1057-2026-f04-thumb.png)](https://wes.copernicus.org/articles/11/1057/2026/wes-11-1057-2026-f04-web.png)

**Figure 4** **(a)** Non-normalized features grouped by similarity under different operating conditions: NO – blue, FC – orange, RI – yellow, and AI – purple. **(b)** Demonstration of the scaling and normalization on the Amp feature related to Eq. ([^7]). Scaled and normalized features grouped by similarity under different conditions **(c)**.

[Download](https://wes.copernicus.org/articles/11/1057/2026/wes-11-1057-2026-f04.png)

The relative change normalization provides a theoretical foundation based on relative scaling and dimensionless feature representation. Figure [^8] a–c illustrates the process: (a) the non-normalized features, (b) the scaling and normalization applied to the Amp feature (extended to all others), and (c) the normalized features obtained using the proposed relative change technique. Features such as energy, kurtosis, higher-order moments, and Shannon entropy exhibited low sensitivity to failures and were excluded during normalization and analysis. This first supervised analysis revealed two feature groups with similar behaviour. Group 1 consists of the RMS and median (Fig. [^8] c, top), while Group 2 comprises the maximum, minimum, amplitude range, variance, energy centre, and signal rate (Fig. [^8] c, bottom). The formation of two feature groups indicates a high degree of correlation within each group, with RMS and median primarily capturing the signal's central tendency. In contrast, the features of Group 2 describe its variability and extremes. Therefore, using all features would introduce redundancy, increase computational cost, and risk overfitting due to the curse of dimensionality. Selecting only representative features from each group ensures that the classifier retains the essential discriminatory information while improving efficiency and generalization.

From the two correlated feature groups, four representative features (RMS, maximum, variance, and amplitude range) were selected to compose the global dataset. Those four features were chosen over the other in their respective group due to near-equivalence, thus avoiding redundancy. The initial global dataset, therefore, consisted of the four selected features extracted from each sensor axis, resulting in a structure of measurement\_rows × 48 columns, plus the SCADA data, as detailed in Table [^4]. However, including all these features may appear arbitrary and degrade model performance due to their high similarity. To refine the global dataset, a canonical correlation analysis was applied to identify the most sensitive features for each sensor, accounting for all axes simultaneously within the sensor group. The highest feature correlation scores were selected, reducing the dataset to four representative features plus SCADA. This process yielded the final datasets: the binary classification dataset has six columns (four features plus SCADA), and the multi-class dataset has nine columns (selected features plus SCADA). Identifying the most informative sensor is also relevant, as it indicates which sensor contributes most to classification accuracy and provides resilience in the event of sensor loss. To validate this study, the most sensitive feature from the best-performing sensor was removed in subsequent tests, thereby demonstrating the robustness and consistency of the proposed feature selection strategy. Feature and sensor selection are detailed in Sect. [2.1](https://wes.copernicus.org/articles/11/1057/2026/#Ch1.S2.SS1).

### Structured final datasets

The final refined dataset organization is a crucial step for enabling machine learning algorithms to accurately classify operational failures. The deployed dataset exhibits a multimodal nature, integrating structural, temperature, and wind velocity information. The structural data are directly acquired from the accelerometers, which capture the system's physical response and potential failure signatures. In contrast, temperature and wind speed data are obtained from the SCADA system and represent indirect but relevant variables that influence the dynamic behaviour measured by the accelerometers. However, they do not directly describe the damage dynamics. The final dataset is organized into four configurations, which are evaluated. Their relevance is demonstrated in Sect. [^12], yielding the following:

- *Fe-kms-Sc*. Dataset composed of the selected features (Fe) extracted from the accelerometer time signals, followed by the SCADA data (Sc) and label defined by the *k* -means clustering (kms),
- *Fe-Sc-kms*. Dataset including the selected features, the SCADA data, and the corresponding *k* -means labels,
- *Fe-kms*. Dataset including the selected features and the *k* -means labels, without incorporating the SCADA information,
- *Fe-kms-LoseSensor*. Dataset including the selected features excluding those obtained from the most sensitive sensor identified by the Fast CCA method, together with the *k* -means labels and SCADA data. This configuration simulates the loss of the most sensitive sensor in each analysis scenario.

The *k* -means labelling of the datasets *Fe-kms-Sc* and *Fe-kms-LoseSensor* is applied exclusively to the features that contain the most relevant physical information about the damage. The SCADA data are then organized by the corresponding day and hour for each feature sample. This ensures that the SCADA records follow the same row reordering imposed by the *k* -means clustering, while preserving the correct temporal (day and hour) correspondence between the SCADA measurements and the related accelerometer data.

The monitoring model integrates sequential stages, starting with data processing and feature extraction, followed by pattern recognition through clustering, and extending to feature and sensor selection to strengthen dataset reliability. By coupling unsupervised clustering with canonical-correlation-based feature selection, the framework ensures the preservation of the most informative variables, thereby enhancing classification accuracy.

## 3.1 Pattern recognition and clustering

Unsupervised pattern recognition, labelling, and clustering of the normalized features were performed using the *k* -means algorithm, with the elbow method applied to determine the optimal number of clusters. The silhouette coefficient and Davies–Bouldin index are internal validation metrics used to assess the number and quality of clusters identified by *k* -means. Table [^9] lists the *k* -means metrics for each sensor and case of study.

**Table 3** *k* -means clustering identification for each sensor related to the failure associated with the silhouette coefficient and Davies–Bouldin index performance metrics.

[![](https://wes.copernicus.org/articles/11/1057/2026/wes-11-1057-2026-t03-thumb.png)](https://wes.copernicus.org/articles/11/1057/2026/wes-11-1057-2026-t03.png)

[Download Print Version](https://wes.copernicus.org/articles/11/1057/2026/wes-11-1057-2026-t03.png) | [Download XLSX](https://wes.copernicus.org/articles/11/1057/2026/wes-11-1057-2026-t03.xlsx)

For binary cases (*k* =2), the results indicate good separability between operating conditions, with consistent metrics across different components and failure types. In NO-FC scenarios, silhouette score values remain high (between 0.86 and 0.87), and Davies–Bouldin indices are low (between 0.12 and 0.13), indicating that points within each group are very similar to each other and that the clusters are well separated. In NO-RI and NO-AI conditions, the results still exhibit a satisfactory clustering structure, with silhouette values ranging from 0.56 to 0.60, and Davies–Bouldin scores between 0.58 and 0.75, indicating good cluster quality. In general, all binary-scenario cases yielded metrics superior to the reference values recommended in the literature (silhouette >0.5 and Davies–Bouldin <1.0), confirming that the clustering method can adequately distinguish the different operational states of the turbines. For the multi-class case with *k* =4, the validation metrics indicate good clustering quality. Silhouette score values range from 0.52 to 0.60, and the Davies–Bouldin index values range from 0.50 to 0.60, indicating compact and well-separated clusters. These results confirm that the clustering process identified variations in turbine operational states. Therefore, these metrics provide strong evidence that the clustering step is reliable and that the labels assigned during the unsupervised phase are consistent.

**Table 4** Explicit description of the datasets used for training, validation, and testing.

[![](https://wes.copernicus.org/articles/11/1057/2026/wes-11-1057-2026-t04-thumb.png)](https://wes.copernicus.org/articles/11/1057/2026/wes-11-1057-2026-t04.png)

[Download Print Version](https://wes.copernicus.org/articles/11/1057/2026/wes-11-1057-2026-t04.png) | [Download XLSX](https://wes.copernicus.org/articles/11/1057/2026/wes-11-1057-2026-t04.xlsx)

The outputs are subsequently used as inputs for the feature and sensor selection. Furthermore, the samples were randomly divided, and the clustered dataset was split into training/validation 75 % and test 25 %, which were used for model construction and evaluation, as shown in Table [^10]. Each classifier was assessed using a 5-fold cross-validation procedure to enhance training accuracy, which was achieved by randomly partitioning the training dataset into five distinct subsets.

## 3.2 Feature and sensor fast selection

The supervised feature analysis indicates that changes in the turbine's dynamic behaviour are associated with specific events. For the subsequent procedures, feature and sensor selection are performed using the canonical-correlation-based feature selection method (FASTCAN) introduced by [Zhang et al.](https://wes.copernicus.org/articles/11/1057/2026/#bib1.bibx65) ([^83]), which was initially applied only for feature selection and is extended in this work to include sensor selection. Therefore, the selection process is carried out in two steps: first, identifying the best feature(s) for each sensor and, second, selecting the most relevant sensor(s). The pseudocode for this process is given in Algorithm [^11], which is repeated for each fault diagnosis. The FASTCAN method is based on the canonical correlation coefficient (CCA), a measure of the linear association between two multivariate random variables. It evaluates the relevance of features with respect to the response matrix. Given the feature matrix $\mathbf{X} \in \mathbb{R}^{N \times n}$ and the response matrix $\mathbf{Y} \in \mathbb{R}^{N \times m}$, the canonical correlation coefficient is defined as

$$
R_{i} \left(\mathbf{X} , \mathbf{Y}\right) = \underset{\mathit{\alpha}_{i} , \mathit{\beta}_{i}}{max} r \left(\mathbf{X}_{C} \mathit{\alpha}_{i} , \mathbf{Y}_{C} \mathit{\beta}_{i}\right) , (\text{2})
$$

where **X** <sub>C</sub> and **Y** <sub>C</sub> are column-centred matrices and $r \left(\cdot , \cdot\right)$ denotes the Pearson correlation. The projection vectors *α* <sub><i>i</i></sub> ∈ℝ <sup><i>n</i></sup> and *β* <sub><i>i</i></sub> ∈ℝ <sup><i>m</i></sup> are obtained by solving the following eigenvalue problems:

$$
\begin{aligned}
(\text{3}) \left(\right. \mathbf{X}_{C}^{\top} \mathbf{X}_{C} \left.\right)^{- 1} \mathbf{X}_{C}^{\top} \mathbf{Y}_{C} \left(\right. \mathbf{Y}_{C}^{\top} \mathbf{Y}_{C} \left.\right)^{- 1} \mathbf{Y}_{C}^{\top} \mathbf{X}_{C} \mathit{\alpha}_{i} = R_{i}^{2} \left(\mathbf{X} , \mathbf{Y}\right) \mathit{\alpha}_{i} \\ (\text{4}) \left(\right. \mathbf{Y}_{C}^{\top} \mathbf{Y}_{C} \left.\right)^{- 1} \mathbf{Y}_{C}^{\top} \mathbf{X}_{C} \left(\right. \mathbf{X}_{C}^{\top} \mathbf{X}_{C} \left.\right)^{- 1} \mathbf{X}_{C}^{\top} \mathbf{Y}_{C} \mathit{\beta}_{i} = R_{i}^{2} \left(\mathbf{X} , \mathbf{Y}\right) \mathit{\beta}_{i} .
\end{aligned}
$$

The eigenvalues $R_{i}^{2} \left(\mathbf{X} , \mathbf{Y}\right)$ correspond to the squared canonical correlation coefficients, while *α* <sub><i>i</i></sub> and *β* <sub><i>i</i></sub> are the canonical weight vectors that define the canonical variates **X** <sub>C</sub> *α* <sub><i>i</i></sub> and **Y** <sub>C</sub> *β* <sub><i>i</i></sub>. There are at most $min \left(n , m\right)$ non-zero canonical correlation coefficients $R_{1} \left(\mathbf{X} , \mathbf{Y}\right) , \ldots , R_{min \left(n , m\right)} \left(\mathbf{X} , \mathbf{Y}\right)$. The overall criterion for feature selection is the sum of squared canonical correlations (SSC):

$$
\text{SSC} \left(\mathbf{X} , \mathbf{Y}\right) = \sum_{k = 1}^{min \left(n , m\right)} R_{k}^{2} \left(\mathbf{X} , \mathbf{Y}\right) . (\text{5})
$$

To accelerate computation, the SSC can be reformulated using two equivalent decompositions: (i) the *h* -correlation form (valid when $N \leq n + m$),

$$
\text{SSC} \left(\mathbf{X} , \mathbf{Y}\right) = \sum_{i = 1}^{n} \sum_{j = 1}^{m} r^{2} \left(w_{i} , v_{j}\right) , (\text{6})
$$

where *{* *w* <sub><i>i</i></sub> *}* and *{* *v* <sub><i>j</i></sub> *}* are orthogonal bases of the feature and response spaces; and (ii) the *θ* -angle form (valid when $N > n + m$),

$$
\text{SSC} \left(\mathbf{X} , \mathbf{Y}\right) = \sum_{i = 1}^{n} \sum_{j = 1}^{m} cos^{2} \left(\angle \left(w_{i} , v_{j}\right)\right) , (\text{7})
$$

where the canonical correlations are expressed as squared cosines of the principal angles between the subspaces of **X** and **Y**. In the greedy selection step, the next feature *x* <sub><i>r</i> <i>i</i></sub> is chosen to maximize the incremental SSC:

$$
d = arg \underset{i}{max} \sum_{k = 1}^{min \left(p + 1 , m\right)} R_{k}^{2} \left(\left(\mathbf{X}_{s} , x_{r i}\right) , \mathbf{Y}\right) , (\text{8})
$$

where **X** <sub>s</sub> denotes the already selected features. This formulation allows efficient feature ranking by reducing computational complexity while preserving the theoretical properties of canonical correlation analysis.

This process involves looping through the features for each sensor in an interaction. In sequence, a similar procedure is performed for sensor ranking, with the feature matrix defined as $\mathbf{X}_{s} \in \mathbb{R}^{S \times s}$, where **X** <sub>s</sub> contains the highest ranking feature(s) of each sensor.

**Algorithm 2** Pseudocode for the feature and sensor selection with canonical correlation.

**Input:** $\mathbf{X} \in \mathbb{R}^{N \times n}$ *Candidate feature matrix*

**Input:** $\mathbf{Y} \in \mathbb{R}^{N \times m}$ *Target multi-label matrix*

**Output:** $\mathbf{d} \in \mathbb{R}^{1 \times \mathcal{T}}$, where $\mathbf{d} = \left(d_{1} , d_{2} , \ldots , d_{t}\right)$ *Index of the feature with the highest ranking score*

**Output:** $\mathbf{q} \in \mathbb{R}^{1 \times s}$, where $\mathbf{q} = \left(q_{1} , q_{2} , \ldots , q_{s}\right)$ *Index of the feature with the highest ranking score associated with the sensor*

1:

𝒯∈ *N* *Number of features to be selected*

2:

s∈S *Number of sensors*

3:

**X** <sub>s</sub> ←0 *Candidate feature matrix coating the best feature(s) of each sensor. The threshold score is* ≥0.6

4:

**for** *j* ←1 to s **do**

5:

$\mathbf{X}_{C} \leftarrow \left[\right. \mathbf{X} - \text{mean} \left(\mathbf{X}\right)$\], $\mathbf{Y}_{C} \leftarrow \left[\mathbf{Y} - \text{mean} \left(\mathbf{Y}\right)\right]$

6:

**if** use *η* -cosine **then**

7:

$$
\left[\mathbf{U} , \mathbf{S} , \mathbf{V}_{h}^{\top}\right] \leftarrow \text{svd} \left(\left[\mathbf{X}_{C} \mid \mathbf{Y}_{C}\right]\right)
$$

8:

$$
\left[\right. \mathbf{X}_{C} \left]\right._{U} \mid \left[\right. \mathbf{Y}_{C} \left]\right._{U} \leftarrow \mathbf{SV}_{h}^{\top}
$$

9:

**end** **if**

10:

$R_{i}^{2} \leftarrow 0$ for $i = 1 , \ldots , n$ *Feature ranking scores*

11:

*d* <sub><i>i</i></sub> ←0 for $i = 1 , \ldots , t$ *Output indices vector, where* *t* ∈ *N* *is the number of features to be selected*

12:

**procedure** FASTCAN X, Y, t, tol, alg *Function described in [Zhang et al.](https://wes.copernicus.org/articles/11/1057/2026/#bib1.bibx65) ([^83])*

13:

$$
d \leftarrow arg max_{j} R_{j}^{2}
$$

14:

**return** **d**

15:

$\mathbf{X}_{s} \leftarrow \mathbf{X} \left[: , max \left(\mathbf{d}\right)\right]$ *Highest score feature*

16:

**end** **for**

17:

**procedure** FASTCAN **X** <sub>s</sub>, Y, s, tol, alg

18:

$$
\text{q} \leftarrow arg max_{j} R_{j}^{2}
$$

19:

**return** q

## 3.3 Classification and model evaluation

ML algorithms are applied to classify the operational condition of the wind turbine by analysing datasets. As an automated approach, ML identifies patterns in data through various algorithms, and uses these learned patterns for predictive analysis and decision-making. The proposed model follows a hybrid unsupervised-supervised ML-based framework, incorporating classification strategies to improve the structure of data attributes. The data-driven ML models are fed selected features extracted from the multiphysics database, incorporating vibration responses and environmental data, and the output corresponds to the wind turbine's operational classification state.

For the classification task, six supervised ML algorithms are utilized, and the unsupervised *k* -means algorithm is used for initial clustering. At the same time, the supervised classifiers Naive Bayes (NB), decision tree (DT), random forest (RF), kNN, SVM, and extreme gradient boosting (XGB) are employed to detect the system's operational conditions. The ML algorithms embedded in the framework are based on the open-source Scikit-learn library. These algorithms perform final classification based on the initial clustering results, producing outputs including confusion matrices and performance metrics. The selection of hyperparameters follows the recommendations in [de Sousa et al.](https://wes.copernicus.org/articles/11/1057/2026/#bib1.bibx19) ([^38]) and [Coelho et al.](https://wes.copernicus.org/articles/11/1057/2026/#bib1.bibx15) ([^35], [^36]), which identified optimal configurations for this application. Specifically, the SVM model employs a linear kernel with a penalty parameter of *C* =100, a one-vs-one multi-class strategy, and a tolerance of $1 \times 10^{- 3}$. For kNN, the number of neighbours is set to *k* =3, using the Euclidean distance metric, uniform weights, and a leaf size of 30. The RF and DT algorithms both use 100 trees, a maximum depth of 3, and the Gini splitting criterion. The Naive Bayes classifier employs a Gaussian model, while XGBoost uses the XGBClassifier implementation. These configurations have shown high accuracy and robustness in prior studies, and are adopted here to optimize classification performance.

The final step involves evaluating model performance on a previously separated test dataset. Hyperparameters may be fine-tuned to improve accuracy, precision, recall, and the F1-score. A confusion matrix is also analysed to provide further diagnostic insight. To prevent overfitting and ensure generalizability, a 5-fold cross-validation scheme is employed. Performance metrics and confusion matrices are generated for all algorithms, enabling the framework to identify the most accurate model and guide users in selecting the most suitable ML algorithm for wind turbine monitoring.

During the monitoring process, data from various sensors are available. To ensure accurate failure identification and classification, it is essential to evaluate the most informative sensor data. In the proposed framework, both features and sensors are ranked and selected to compose the reduced dataset, ensuring that only the most sensitive information related to the specific failure is included and fed into the ML algorithm for wind turbine condition classification. The feature and sensor scores, normalized to the range \[0, 1\], are returned by the CCA's ranking process. Further, the dataset for the ML algorithms was built by selecting the top-ranked features from each sensor, along with the SCADA wind speed and temperature.

The evaluation of the turbine's operational condition includes both binary and multi-class classification tasks. Table [^13] summarizes the failure cases related to the most sensitive feature of each sensor (*X* <sub>s</sub>) and the most sensitive sensor associated with its features for each failure.

**Table 5** Description of the sensitive feature of each sensor (X <sub>s</sub>) and an indication of the most sensitive sensor of each failure case.

[![](https://wes.copernicus.org/articles/11/1057/2026/wes-11-1057-2026-t05-thumb.png)](https://wes.copernicus.org/articles/11/1057/2026/wes-11-1057-2026-t05.png)

[Download Print Version](https://wes.copernicus.org/articles/11/1057/2026/wes-11-1057-2026-t05.png) | [Download XLSX](https://wes.copernicus.org/articles/11/1057/2026/wes-11-1057-2026-t05.xlsx)

[![https://wes.copernicus.org/articles/11/1057/2026/wes-11-1057-2026-f05](https://wes.copernicus.org/articles/11/1057/2026/wes-11-1057-2026-f05-thumb.png)](https://wes.copernicus.org/articles/11/1057/2026/wes-11-1057-2026-f05-web.png)

**Figure 5** CCA feature score and dispersion diagrams of the highest-scoring feature for the NO-FC failure: **(a)** sensor MSH, **(b)** sensor L05 (1 and 2), **(c)** sensor GEN, and **(d)** sensor NMF (1 and 2).

[Download](https://wes.copernicus.org/articles/11/1057/2026/wes-11-1057-2026-f05.png)

[![https://wes.copernicus.org/articles/11/1057/2026/wes-11-1057-2026-f06](https://wes.copernicus.org/articles/11/1057/2026/wes-11-1057-2026-f06-thumb.png)](https://wes.copernicus.org/articles/11/1057/2026/wes-11-1057-2026-f06-web.png)

**Figure 6** CCA feature score and dispersion diagrams of the highest-scoring feature for the NO-RI failure: **(a)** sensor MSH, **(b)** sensor L05 (1 and 2), **(c)** sensor GEN, and **(d)** sensor NMF (1 and 2).

[Download](https://wes.copernicus.org/articles/11/1057/2026/wes-11-1057-2026-f06.png)

[![https://wes.copernicus.org/articles/11/1057/2026/wes-11-1057-2026-f07](https://wes.copernicus.org/articles/11/1057/2026/wes-11-1057-2026-f07-thumb.png)](https://wes.copernicus.org/articles/11/1057/2026/wes-11-1057-2026-f07-web.png)

**Figure 7** CCA feature score and dispersion diagrams of the highest-scoring feature for the NO-AI failure: **(a)** sensor MSH, **(b)** sensor L05 (1 and 2), **(c)** sensor GEN, and **(d)** sensor NMF (1 and 2).

[Download](https://wes.copernicus.org/articles/11/1057/2026/wes-11-1057-2026-f07.png)

[![https://wes.copernicus.org/articles/11/1057/2026/wes-11-1057-2026-f08](https://wes.copernicus.org/articles/11/1057/2026/wes-11-1057-2026-f08-thumb.png)](https://wes.copernicus.org/articles/11/1057/2026/wes-11-1057-2026-f08-web.png)

**Figure 8** Sensor score based on the top-performing features of each operational condition: **(a)** NO-FC, **(b)** NO-AI, **(c)** NO-RI, and **(d)** multi-class.

[Download](https://wes.copernicus.org/articles/11/1057/2026/wes-11-1057-2026-f08.png)

For binary classification between NO and FC failure, the individual feature scores for each accelerometer sensor are shown in Fig. [^14] a–d. Subsequently, in the sensor ranking, the NMF sensor (RMS\_X02 <sup>NMF</sup>) yields the highest score, indicating it as the most sensitive to FC-related failures, as shown in Fig. [^17] a. The *k* -means algorithm is applied to label and organize the data based on similarities among the selected features. Incorporating more informative features improves both pattern recognition and classification accuracy. Each feature is visualized individually for clarity, and the final classification integrates all selected features along with SCADA data to strengthen the overall decision-making process. Features with minimal overlap between operational states are especially valuable, as they contribute to clearer distinctions and improved ML performance in identifying fault conditions. Scatter plots in Fig. [^14] e–h display the correlation between Feature-1 and Feature-2, which represent two groups derived from splitting each selected feature column. These diagrams highlight how high-scoring features cluster across sensors, revealing patterns that differentiate between normal and faulty operating conditions. The identified clusters exhibit consistent grouping and dispersion, thereby enhancing the interpretability of each operational condition.

For classification between NO and RI, the feature scores for each accelerometer are shown in Fig. [^15] a–d and Table [^13], with the MSH sensor (RMS\_X02 <sup>MSH</sup>) achieving the highest score, indicating strong sensitivity to RI-related anomalies, as indicated in Fig. [^17] b. The *k* -means clustering is applied to the selected features to identify patterns and assign labels. Scatter plots in Fig. [^15] e–h display the highest-scoring feature pairs (Feature-1 vs Feature-2) per sensor, revealing clear cluster separation between NO and RI. These dispersion diagrams highlight how specific failures impact dynamic behaviour, with minimal overlap between classes indicating highly informative features for classification. For the NO-AI, the feature ranking scores of each accelerometer are presented in Fig. [^16] a–d, where the NMF sensor (RMS\_X02 <sup>NMF</sup>) shows the highest relevance, indicating strong responsiveness to RI-related conditions – see Fig. [^17] c. The *k* -means clustering is applied to the selected features to identify patterns and assign labels. The resulting scatter plots in Fig. [^16] e–h show the top-ranked feature pairs (Feature-1 vs Feature-2) for each sensor, revealing distinct cluster boundaries between NO and AI. These diagrams illustrate how different faults affect the turbine's dynamic behaviour, with low class overlap indicating that the selected features are highly effective for classification.

In the multi-class classification, the *k* -means algorithm identifies four clusters corresponding to NO, FC, RI, and AI conditions, organizing the dataset accordingly into response clusters. These clusters support further validation of classification through performance metrics. Figure [^18] displays the highest-scoring features of each sensor and their related dispersion diagrams, labelled by *k* -means and ranked by Algorithm [^11], respectively. Each class is colour-coded to facilitate quick visual identification and analysis of overlaps between operational states.

[![https://wes.copernicus.org/articles/11/1057/2026/wes-11-1057-2026-f09](https://wes.copernicus.org/articles/11/1057/2026/wes-11-1057-2026-f09-thumb.png)](https://wes.copernicus.org/articles/11/1057/2026/wes-11-1057-2026-f09-web.png)

**Figure 9** CCA feature score and dispersion diagrams of the highest-scoring feature: **(a)** sensor MSH, **(b)** sensor L05 (1 and 2), **(c)** sensor GEN, and **(d)** sensor NMF (1 and 2).

[Download](https://wes.copernicus.org/articles/11/1057/2026/wes-11-1057-2026-f09.png)

Figure [^18] a–d gives the top-ranked features from each sensor, MSH, L05, NMF, and GEN, respectively, highlighting the most sensitive sensors selected for multi-class classification. Likewise, in the binary case, features with higher scores are included in the global dataset for classification, with the GEN and NMF sensors showing the highest relevance, indicating strong sensitivity, as shown in Fig. [^17] d. Each selected feature is visualized through its dispersion correlation, also in Fig. [^18] a–d. Overall, *k* -means effectively assigns each operational fault to a class. Certain features exhibit a clear separation between normal conditions and fault types, although overlap among fault classes is evident in all cases. This suggests that while individual features may help to detect abnormal behaviour, they are not self-sufficient alone to discriminate between specific failure modes. These individual feature analyses reveal important patterns. However, when classification models are applied, features are considered in combination. This integrated approach improves both classification accuracy and the robustness of the performance metrics. While some features aid in distinguishing normal from faulty states, reliable fault classification generally requires the combined contribution of multiple informative features.

## Operational condition classification and metrics evaluation

The fault classification uses six supervised machine learning algorithms: kNN, SVM, DT, RF, Naive Bayes, and XGBoost. These algorithms perform the final classification using the input dataset, producing confusion matrices and performance metrics. The selection of hyperparameters is based on the investigations of [de Sousa et al.](https://wes.copernicus.org/articles/11/1057/2026/#bib1.bibx19) ([^38]), which specify optimal configurations for this assignment and are briefly described in Sect. [3.3](https://wes.copernicus.org/articles/11/1057/2026/#Ch1.S3.SS3).

[![https://wes.copernicus.org/articles/11/1057/2026/wes-11-1057-2026-f10](https://wes.copernicus.org/articles/11/1057/2026/wes-11-1057-2026-f10-thumb.png)](https://wes.copernicus.org/articles/11/1057/2026/wes-11-1057-2026-f10-web.png)

**Figure 10** Comparison of the metrics (accuracy, F1-score, precision, recall, and cross-validation) for the six ML algorithms and each arranged final dataset. **(a)** Binary NO-FC, **(b)** binary NO-AI, **(c)** binary NO-RI, and **(d)** multi-class failure study cases.

[Download](https://wes.copernicus.org/articles/11/1057/2026/wes-11-1057-2026-f10.png)

Figure [^19] presents the performance of ML models for binary classification (NO-FC, NO-RI, and NO-AI) and multiple failure conditions, evaluated via cross-validation and metrics such as accuracy, precision, recall, and F1-score. For metric estimation, micro-, macro-, and weighted averages were tested, assuming the micro as the standard because it computes classification metrics by globally summing true positives, false positives, and false negatives across all classes, resulting in similar precision, recall, and F1-score.

The ML models were tested on the *Fe-kms-Sc*, *Fe-Sc-kms*, *Fe-kms*, and *Fe-kms-LoseSensor* datasets to assess the influence of environmental dependencies (SCADA data) and the sensitivity of each sensor in failure evaluation. The metrics for the *Fe-Sc-kms* dataset, shown as black (∗) in Fig. [^19] a–d, indicate that, except for the NB classifier, all ML models achieved 100 % accuracy. Such a perfect performance across multiple models can suggest potential issues, such as data leakage, overfitting, or improper dataset splitting. However, cross-validation with multiple random partitions was performed to ensure statistical robustness. In this case, the consistently high accuracy reflects the physical consistency and strong discriminative power of the selected features rather than methodological flaws.

The *k* -means clustering results and associated metrics also reveal clear class separation. The feature scores derived from the CCA, which quantify the linear association between the selected features and the *k* -means clusters (Fig. [^20]), highlight the strong correlation between SCADA data and the structural sensors (accelerometers). The SCADA system provides environmental variables, such as daily temperature and wind speed but lacks important structural information more directly related to damage states. In the *Fe-Sc-kms* dataset configuration, both features and SCADA inputs are used in the *k* -means clustering, which is predominantly influenced by the SCADA parameters. This result is supported by [Wang et al.](https://wes.copernicus.org/articles/11/1057/2026/#bib1.bibx63) ([^81]). Therefore, the perfect ML metrics are attributed to dataset bias, where the models primarily classify failure conditions based on environmental variations rather than the structural response itself.

[![https://wes.copernicus.org/articles/11/1057/2026/wes-11-1057-2026-f11](https://wes.copernicus.org/articles/11/1057/2026/wes-11-1057-2026-f11-thumb.png)](https://wes.copernicus.org/articles/11/1057/2026/wes-11-1057-2026-f11-web.png)

**Figure 11** Feature score of the *Fe-Sc-kms* dataset for **(a)** NO-FC, **(b)** NO-RI, **(c)** NO-AI, and **(d)** multi-class.

[Download](https://wes.copernicus.org/articles/11/1057/2026/wes-11-1057-2026-f11.png)

The models' metrics for the *Fe-kms-Sc* dataset, shown as blue (•) in Fig. [^19] a–d, indicate the sensitivity of the ML algorithms to the failure classification. The *k* -means is performed on the structural features, and the SCADA follows its data reorganization, but it is not directly considered in the *k* -means labelling. For the binary case, the model's metrics range from 0.93 to 0.99. The SVM model reached 0.98 on the NO-FC case, XGBoost reached 0.98 for NO-AI, and XGBoost reached 0.99 for NO-RI. The multi-class case varied from 0.86 by NB to 0.955 by RF. The SCADA data are not included in the *Fe-kms* dataset, shown as orange (▪) in Fig. [^19] a–d. The performance metrics reached 0.98 with the SVM model for the NO-FC case, 0.955 with RF for the NO-AI case, 0.98 with XGBoost for the NO-RI case, and 0.95 with RF in the multi-class analysis. When the most sensitive sensor for each failure case was removed from the *Fe-kms-LoseSensor* dataset (yellow ⧫), performance metrics decreased, except for NO-AI, indicating the importance of this sensor's information for monitoring accuracy and model performance. This result also reinforces the fact that the most sensitive sensor is typically located near the damage site. In the NO-AI case, all sensors were positioned on the nacelle and tower. Although these sensors can capture the dynamic effects of blade aero-imbalance, they are distant from the local damage, which reduces their sensitivity to this phenomenon. Consequently, the sensor group primarily captured global structural responses to the fault rather than local damage effects, which explains the variation in performance when one sensor was removed.

[![https://wes.copernicus.org/articles/11/1057/2026/wes-11-1057-2026-f12](https://wes.copernicus.org/articles/11/1057/2026/wes-11-1057-2026-f12-thumb.png)](https://wes.copernicus.org/articles/11/1057/2026/wes-11-1057-2026-f12-web.png)

**Figure 12** Confusion matrix of binary operational classification for **(a)** NO-FC, **(b)** NO-RI, **(c)** NO-AI, and **(d)** multi-classification. The dataset assumes the best features plus SCADA data (temperature and wind speed) in each analysis.

[Download](https://wes.copernicus.org/articles/11/1057/2026/wes-11-1057-2026-f12.png)

The confusion matrices shown in Fig. [^21] a–c present the results of binary classification using the respective best-performing ML algorithms using the *Fe-kms-Sc* dataset. In the NO-FC case, the SVM model achieved optimal accuracy and cross-validation, correctly classifying 292 samples as NO (65.47 %) and 146 as FC (32.74 %). For the NO-RI classification, the XGBoost model correctly classifies 210 samples as NO (63.06 %) and 119 as RI (35.74 %). In the NO-AI scenario, the XGBoost model outperformed the others, correctly classifying 101 samples as AI (40.08 %) and 147 as NO (58.33 %). Figure [^21] d displays the confusion matrix for the multi-class classification involving AI, FC, NO, and RI. The RF model correctly identified 139 samples as AI (17.64 %), 185 as FC (23.48 %), 178 as RI (22.59 %), and 251 as NO (31.85 %).

Among the evaluated configurations, the *Fe-kms-Sc* dataset provided the most balanced and reliable results for the treated failure identification, including structural and environmental condition information. The dataset *Fe-Sc-kms* yielded perfect metrics across all models, primarily because environmental parameters, such as temperature and wind speed, were dominant, biasing the classification towards environmental conditions rather than structural responses. In contrast, excluding SCADA data (*Fe-kms*) enabled the models to capture damage-related structural dynamics more accurately, but it did not account for environmental variability. The *Fe-kms-LoseSensor* results highlighted the critical role of the most sensitive sensor, typically located near the damage, in maintaining model accuracy. Overall, the *Fe-kms-Sc* dataset, which integrates structural features with aligned but non-dominant environmental information, yielded the most physically consistent and discriminative performance for the wind turbine failure classification.

This study proposes a data-driven hybrid framework for classifying operational conditions of a wind turbine, including normal operation, pitch drive faults, rotor icing, and aerodynamic imbalance, integrating in a hybrid approach multimodal data and multiple ML algorithms. The monitoring process follows this pipeline: data processing and organization, feature extraction, normalization and grouping, clustering, feature and sensor selection, data splitting, machine learning classification, and model evaluation. A novel relative change damage index was introduced to enhance scalability and normalize features extracted from structural dynamic responses and environmental conditions. Canonical correlation analysis was used to identify and rank the most sensitive features among the 15 extracted from temporal responses and SCADA data (wind speed and temperature), and to rank sensors. Thus, multimodal information, including vibration signals from six accelerometers distributed across the turbine and environmental parameters(wind speed and temperature), was incorporated into the framework. Unsupervised *k* -means clustering enabled the discovery of homogeneous data groups, supporting robust pattern recognition without predefined labels.

Failure classification was implemented as both binary and multi-class tasks using kNN, SVM, DT, RF, Naive Bayes, and XGBoost. Models were tested on the *Fe-kms-Sc*, *Fe-Sc-kms*, *Fe-kms*, and *Fe-kms-LoseSensor* datasets to evaluate the influence of environmental factors and sensor sensitivity. Using the *Fe-kms-Sc* dataset, the models performed best, where SVM achieved the highest accuracy for NO-FC (0.98), XGBoost for NO-RI (0.99) and NO-AI (0.98), and RF for multi-class classification (0.955). The *Fe-kms-Sc* dataset, which combines structural features with aligned SCADA data, yielded the most reliable failure detection. Excluding SCADA data (*Fe-kms*), the models focused on structural changes, with binary accuracies of 0.93–0.99 and multi-class accuracies of 0.86–0.95. Including SCADA alone (*Fe-Sc-kms*) produced perfect metrics due to environmental dominance, whereas removing the most sensitive sensor (*Fe-kms-LoseSensor*) reduced performance, confirming the importance of sensor placement near the damage and identifying the most sensitive sensor in each analysis.

The proposed hybrid model, developed and tested on a 6.7 kW Aventa turbine, effectively manages the complexity of multi-source turbine data and representative fault variations. Its success relies on careful feature and sensor selection, ML model selection, the inclusion of environmental data, dataset multimodality, and thoughtful dataset arrangement, which together enhance discriminative power and classification reliability. However, validation is limited by the small size of the wind turbine, the use of induced faults to simulate aero-imbalance in the blades, and differences between small-scale experimental turbines and large-scale operational turbines or wind farms. Extreme environmental and operational events, such as strong turbulence, large-scale icing, and mixed-fault scenarios, were not included in this study due to the controlled nature and limited scope of the experimental datasets. Ongoing studies aim to evaluate the methodology on larger, more diverse datasets; to further explore environmental effects; to extend the study to offshore wind farms; and to assess the reliability, generalization, and applicability to utility-scale systems.

The underlying code for this study is available at [https://github.com/iMOSS-Lab/rp-wedowind-challenge](https://github.com/iMOSS-Lab/rp-wedowind-challenge-ASCE-EMI) [\-ASCE-EMI](https://github.com/iMOSS-Lab/rp-wedowind-challenge-ASCE-EMI) (last access: 20 March 2026) and [https://doi.org/10.5281/zenodo.18940555](https://doi.org/10.5281/zenodo.18940555) ([Machado](https://wes.copernicus.org/articles/11/1057/2026/#bib1.bibx42), [^60]).

The public data used in this article can be accessed at [https://doi.org/10.5281/zenodo.8229750](https://doi.org/10.5281/zenodo.8229750) ([Chatzi et al.](https://wes.copernicus.org/articles/11/1057/2026/#bib1.bibx13), [^33]).

All authors contributed to the conceptualization and methodology. AASRS and JSC carried out data curation, formal analysis, investigation, and software development. MRM and ROL were responsible for funding acquisition, project administration, resources, and supervision. MRM prepared the paper, with contributions from all co-authors.

The contact author has declared that none of the authors has any competing interests.

Publisher's note: Copernicus Publications remains neutral with regard to jurisdictional claims made in the text, published maps, institutional affiliations, or any other geographical representation in this paper. The authors bear the ultimate responsibility for providing appropriate place names. Views expressed in the text are those of the authors and do not necessarily reflect the views of the publisher.

This research is part of project no. 444595/2024-4, funded by the National Council for Scientific and Technological Development-CNPq. Marcela Rodrigues Machado acknowledges the sponsors of projects (CNPq, Capes Finance Code 001, and FAPDF.00193-00002143/2023-02).

This research has been supported by the Conselho Nacional de Desenvolvimento Científico e Tecnológico (grant no. 444595/2024-4).

This paper was edited by Yi Guo and reviewed by three anonymous referees.

Amin, A., Bibo, A., Panyam, M., and Tallapragada, P.: Vibration based fault diagnostics in a wind turbine planetary gearbox using machine learning, Wind Engineering, 47, 175–189, [https://doi.org/10.1177/0309524X221123968](https://doi.org/10.1177/0309524X221123968), 2023. [a](https://wes.copernicus.org/articles/11/1057/2026/#xref_text.38)

Ángel Encalada-Dávila, Vidal, Y., and Tutivén, C.: Strain virtual sensor for offshore wind turbine jacket supports: A time series transformer approach validated with Alpha Ventus wind farm data, Mech. Syst. Signal Pr., 231, 112653, [https://doi.org/10.1016/j.ymssp.2025.112653](https://doi.org/10.1016/j.ymssp.2025.112653), 2025. [a](https://wes.copernicus.org/articles/11/1057/2026/#xref_paren.14)

Antoniadou, I., Dervilis, N., Barthorpe, R. J., Manson, G., and Worden, K.: Advanced tools for damage detection in wind turbines, Key Engineering Materials, 569–570, 547–554, [https://doi.org/10.4028/www.scientific.net/KEM.569-570.547](https://doi.org/10.4028/www.scientific.net/KEM.569-570.547), 2013. [a](https://wes.copernicus.org/articles/11/1057/2026/#xref_paren.16)

Antoniadou, I., Dervilis, N., Papatheou, E., Maguire, A. E., and Worden, K.: Aspects of structural health and condition monitoring of offshore wind turbines, Philos. T. R. Soc. A, 373, [https://doi.org/10.1098/rsta.2014.0075](https://doi.org/10.1098/rsta.2014.0075), 2015a. [a](https://wes.copernicus.org/articles/11/1057/2026/#xref_paren.16)

Antoniadou, I., Dervilis, N., Papatheou, E., Maguire, A. E., and Worden, K.: Aspects of structural health and condition monitoring of offshore wind turbines, Philos. T. R. Soc. A, 373, 20140075, [https://doi.org/10.1098/rsta.2014.0075](https://doi.org/10.1098/rsta.2014.0075), 2015b. [a](https://wes.copernicus.org/articles/11/1057/2026/#xref_text.11)

Ashkarkalaei, M., Ghiasi, R., Pakrashi, V., and Malekjafarian, A.: Feature selection for unsupervised defect detection of a wind turbine blade considering operational and environmental conditions, Mech. Syst. Signal Pr., 230, 112568, [https://doi.org/10.1016/j.ymssp.2025.112568](https://doi.org/10.1016/j.ymssp.2025.112568), 2025a. [a](https://wes.copernicus.org/articles/11/1057/2026/#xref_text.23), [b](https://wes.copernicus.org/articles/11/1057/2026/#xref_paren.42)

Ashkarkalaei, M., Ghiasi, R., Pakrashi, V., and Malekjafarian, A.: Optimum feature selection for the supervised damage classification of an operating wind turbine blade, Struct. Health Monit., 0, 1475, [https://doi.org/10.1177/14759217251313815](https://doi.org/10.1177/14759217251313815), 2025b. [a](https://wes.copernicus.org/articles/11/1057/2026/#xref_text.23)

Asian, S., Ertek, G., Haksoz, C., Pakter, S., and Ulun, S.: Wind Turbine Accidents: A Data Mining Study, IEEE Syst. J., 11, 1567–1578, [https://doi.org/10.1109/JSYST.2016.2565818](https://doi.org/10.1109/JSYST.2016.2565818), 2017. [a](https://wes.copernicus.org/articles/11/1057/2026/#xref_paren.2)

Baquerizo, J., Tutivén, C., Puruncajas, B., Vidal, Y., and Sampietro, J.: Siamese Neural Networks for Damage Detection and Diagnosis of Jacket-Type Offshore Wind Turbine Platforms, Mathematics, 10, [https://doi.org/10.3390/math10071131](https://doi.org/10.3390/math10071131), 2022. [a](https://wes.copernicus.org/articles/11/1057/2026/#xref_text.10)

Barreto, L. S., Machado, M. R., Santos, J. C., De Moura, B. B., and Khalij, L.: Damage indices evaluation for one-dimensional guided wave-based structural health monitoring, Lat. Am. J. Solids Stru., 18, 1–17, 2021. [a](https://wes.copernicus.org/articles/11/1057/2026/#xref_paren.42)

Bishop, C. M.: Pattern Recognition and Machine Learning, Springer, 2nd edn., ISBN 978-1493938438, 2006. [a](https://wes.copernicus.org/articles/11/1057/2026/#xref_paren.41)

Carmona-Troyo, J. A., Trujillo, L., Enríquez-Zárate, J., Hernandez, D. E., and Cárdenas-Florido, L. A.: Classification of Damage on Wind Turbine Blades Using Automatic Machine Learning and Pressure Coefficient, Expert Systems, 42, e70024, [https://doi.org/10.1111/exsy.70024](https://doi.org/10.1111/exsy.70024), 2025. [a](https://wes.copernicus.org/articles/11/1057/2026/#xref_paren.9)

Chatzi, E., Abdallah, I., Hofsäß, M., Bischoff, O., Barber, S., and Marykovskiy, Y.: Aventa AV-7 ETH Zurich Research Wind Turbine SCADA and high frequency Structural Health Monitoring (SHM) data, Zenodo \[data set\], [https://doi.org/10.5281/zenodo.8229750](https://doi.org/10.5281/zenodo.8229750), 2023. [a](https://wes.copernicus.org/articles/11/1057/2026/#xref_text.39), [b](https://wes.copernicus.org/articles/11/1057/2026/#xref_paren.40), [c](https://wes.copernicus.org/articles/11/1057/2026/#xref_paren.50)

Civera, M. and Surace, C.: Non-Destructive Techniques for the Condition and Structural Health Monitoring of Wind Turbines: A Literature Review of the Last 20 Years, Sensors, 22, [https://doi.org/10.3390/s22041627](https://doi.org/10.3390/s22041627), 2022. [a](https://wes.copernicus.org/articles/11/1057/2026/#xref_paren.6)

Coelho, J. S., Machado, M. R., Dutkiewicz, M., and O. Teloli, R.: Data-driven machine learning for pattern recognition and detection of loosening torque in bolted joints, J. Braz. Soc. Mech. Sci., 46, [https://doi.org/10.1007/s40430-023-04628-6](https://doi.org/10.1007/s40430-023-04628-6), 2024. [a](https://wes.copernicus.org/articles/11/1057/2026/#xref_text.46)

Coelho, J. S., Machado, M. R., and Dutkiewicz, M.: Integrating Virtual Sensor Data Augmentation Into Machine Learning for Damage Quantification of Bolted Structures Under Assembly Uncertainty, Structural Control and Health Monitoring, 2025, 8030 303, [https://doi.org/10.1155/stc/8030303](https://doi.org/10.1155/stc/8030303), 2025. [a](https://wes.copernicus.org/articles/11/1057/2026/#xref_text.46)

Dervilis, N., Choi, M., Antoniadou, I., Farinholt, K. M., Taylor, S. G., Barthorpe, R. J., Park, G., Farrar, C. R., and Worden, K.: Machine learning applications for a wind turbine blade under continuous fatigue loading, Key Eng. Mat., 588, 166–174, [https://doi.org/10.4028/www.scientific.net/KEM.588.166](https://doi.org/10.4028/www.scientific.net/KEM.588.166), 2014a. [a](https://wes.copernicus.org/articles/11/1057/2026/#xref_text.17)

Dervilis, N., Choi, M., Taylor, S., Barthorpe, R., Park, G., Farrar, C., and Worden, K.: On damage diagnosis for a wind turbine blade using pattern recognition, J. Sound Vib., 333, 1833–1850, [https://doi.org/10.1016/j.jsv.2013.11.015](https://doi.org/10.1016/j.jsv.2013.11.015), 2014b. [a](https://wes.copernicus.org/articles/11/1057/2026/#xref_text.17)

de Sousa, A. A. S. R., da Silva Coelho, J., Machado, M. R., and Dutkiewicz, M.: Multiclass Supervised Machine Learning Algorithms Applied to Damage and Assessment Using Beam Dynamic Response, J. Vib. Eng. Technol., 11, 2709–2731, [https://doi.org/10.1007/s42417-023-01072-7](https://doi.org/10.1007/s42417-023-01072-7), 2023. [a](https://wes.copernicus.org/articles/11/1057/2026/#xref_text.45), [b](https://wes.copernicus.org/articles/11/1057/2026/#xref_text.47)

Dutkiewicz, M. and Machado, M.: Measurements in Situ and Spectral Analysis of Wind Flow Effects on Overhead Transmission Lines, Sound & Vibration, 53, 161–175, [https://doi.org/10.32604/sv.2019.04803](https://doi.org/10.32604/sv.2019.04803), 2019a. [a](https://wes.copernicus.org/articles/11/1057/2026/#xref_paren.2)

Dutkiewicz, M. and Machado, M.: Spectral Approach in Vibrations of Overhead Transmission Lines, IOP Conference Series: Materials Science and Engineering, 471, Session 4, [https://doi.org/10.1088/1757-899x/471/5/052029](https://doi.org/10.1088/1757-899x/471/5/052029), 2019b. [a](https://wes.copernicus.org/articles/11/1057/2026/#xref_paren.4)

Dutkiewicz, M. and Machado, M.: Dynamic Response of Overhead Transmission Line in Turbulent Wind Flow with Application of the Spectral Element Method, IOP Conference Series: Materials Science and Engineering, 471, Session 5, [https://doi.org/10.1088/1757-899x/471/5/052031](https://doi.org/10.1088/1757-899x/471/5/052031), 2019c. [a](https://wes.copernicus.org/articles/11/1057/2026/#xref_paren.4)

Dwivedi, D., Babu, K. V. S. M., Yemula, P. K., Chakraborty, P., and Pal, M.: Identification of surface defects on solar PV panels and wind turbine blades using attention based deep learning model, Eng. Appl. Artif. Intel., 131, 107836, [https://doi.org/10.1016/j.engappai.2023.107836](https://doi.org/10.1016/j.engappai.2023.107836), 2024. [a](https://wes.copernicus.org/articles/11/1057/2026/#xref_paren.8)

Elforjani, M.: Diagnosis and prognosis of real world wind turbine gears, Renew. Energ., 147, 1676–1693, [https://doi.org/10.1016/j.renene.2019.09.109](https://doi.org/10.1016/j.renene.2019.09.109), 2020. [a](https://wes.copernicus.org/articles/11/1057/2026/#xref_paren.32)

Farrar, C. R. and Worden, K.: Structural Health Monitoring: A Machine Learning Perspective, ISBN 9781119994336, [https://doi.org/10.1002/9781118443118](https://doi.org/10.1002/9781118443118), 2012. [a](https://wes.copernicus.org/articles/11/1057/2026/#xref_paren.7)

Figueiredo, E., Park, G., Farrar, C. R., Worden, K., and Figueiras, J.: Machine learning algorithms to damage detection under operational and environmental variability, P. Soc. Photo-Opt. Ins., 7650, [https://doi.org/10.1117/12.849189](https://doi.org/10.1117/12.849189), 2010. [a](https://wes.copernicus.org/articles/11/1057/2026/#xref_paren.5)

Flah, M., Nunez, I., Chaabene, W. B., and Nehdi, M.: Machine Learning Algorithms in Civil Structural Health Monitoring: A Systematic Review, Arch. Comput. Method. E., 28, 2621–2643, [https://doi.org/10.1007/s11831-020-09471-9](https://doi.org/10.1007/s11831-020-09471-9), 2020. [a](https://wes.copernicus.org/articles/11/1057/2026/#xref_paren.7)

Gao, Q., Wu, X., Guo, J., Zhou, H., and Ruan, W.: Machine-Learning-Based Intelligent Mechanical Fault Detection and Diagnosis of Wind Turbines, Math. Probl. Eng., 2021, [https://doi.org/10.1155/2021/9915084](https://doi.org/10.1155/2021/9915084), 2021. [a](https://wes.copernicus.org/articles/11/1057/2026/#xref_text.34)

Hoxha, E., Vidal, Y., and Pozo, F.: Damage Diagnosis for Offshore Wind Turbine Foundations Based on the Fractal Dimension, Appl. Sci., 10, [https://doi.org/10.3390/app10196972](https://doi.org/10.3390/app10196972), 2020. [a](https://wes.copernicus.org/articles/11/1057/2026/#xref_text.27)

Joshuva, A. and Sugumaran, V.: A data driven approach for condition monitoring of wind turbine blade using vibration signals through best-first tree algorithm and functional trees algorithm: A comparative study, ISA Transactions, 67, 160–172, [https://doi.org/10.1016/j.isatra.2017.02.002](https://doi.org/10.1016/j.isatra.2017.02.002), 2017. [a](https://wes.copernicus.org/articles/11/1057/2026/#xref_paren.18)

Joshuva, A., Vishnuvardhan, R., Deenadayalan, G., Sathishkumar, R., and Sivakumar, S.: Implementation of rule based classifiers for wind turbine blade fault diagnosis using vibration signals, International Journal of Recent Technology and Engineering, 8, 320–331, [https://doi.org/10.35940/ijrte.B1050.0982S1119](https://doi.org/10.35940/ijrte.B1050.0982S1119), 2019. [a](https://wes.copernicus.org/articles/11/1057/2026/#xref_paren.18)

Knittel, D., Makich, H., and Nouari, M.: Milling diagnosis using artificial intelligence approaches, Software Impacts, 20, 809, [https://doi.org/10.1051/meca/2020053](https://doi.org/10.1051/meca/2020053), 2019. [a](https://wes.copernicus.org/articles/11/1057/2026/#xref_paren.42)

Korolis, J. S., Bourdalos, D. M., and Sakellariou, J. S.: Machine Learning-Based Damage Diagnosis in Floating Wind Turbines Using Vibration Signals: A Lab-Scale Study Under Different Wind Speeds and Directions, Sensors, 25, [https://doi.org/10.3390/s25041170](https://doi.org/10.3390/s25041170), 2025. [a](https://wes.copernicus.org/articles/11/1057/2026/#xref_paren.24)

Krishna, S. R., Sathish, J., Tarun, M., Rahul Mani Datta, T., and Vamsi, S. Raghu, a. S. S. J.: Machine Learning-Enabled Crack Diagnosis and Prognosis in Glass/Carbon Fiber Composite Structures, Iranian Journal of Science and Technology, Transactions of Mechanical Engineering, 49, 1511–1530, [https://doi.org/10.1007/s40997-025-00855-5](https://doi.org/10.1007/s40997-025-00855-5), 2025. [a](https://wes.copernicus.org/articles/11/1057/2026/#xref_text.13)

Kuai, H., Civera, M., Coletta, G., Chiaia, B., and Surace, C.: Cointegration strategy for damage assessment of offshore platforms subject to wind and wave forces, Ocean Eng., 304, 117692, [https://doi.org/10.1016/j.oceaneng.2024.117692](https://doi.org/10.1016/j.oceaneng.2024.117692), 2024. [a](https://wes.copernicus.org/articles/11/1057/2026/#xref_paren.25)

Kuo, J.-Y., You, S.-Y., Lin, H.-C., Hsu, C.-Y., and Lei, B.: Constructing Condition Monitoring Model of Wind Turbine Blades, Mathematics, 10, [https://doi.org/10.3390/math10060972](https://doi.org/10.3390/math10060972), 2022. [a](https://wes.copernicus.org/articles/11/1057/2026/#xref_paren.9)

Lei, Z., Lin, H., Tang, X., Xiong, Y., and Wen, H.: Wind Turbine Blade Fault Detection Method Based on TROA-SVM, Sensors, 25, [https://doi.org/10.3390/s25030720](https://doi.org/10.3390/s25030720), 2025. [a](https://wes.copernicus.org/articles/11/1057/2026/#xref_paren.9)

Leon-Medina, J. X., Anaya, M., Parés, N., Tibaduiza, D. A., and Pozo, F.: Structural Damage Classification in a Jacket-Type Wind-Turbine Foundation Using Principal Component Analysis and Extreme Gradient Boosting, Sensors, 21, [https://doi.org/10.3390/s21082748](https://doi.org/10.3390/s21082748), 2021. [a](https://wes.copernicus.org/articles/11/1057/2026/#xref_text.29)

Li, W., Zhao, W., Wang, T., and Du, Y.: Surface Defect Detection and Evaluation Method of Large Wind Turbine Blades Based on an Improved Deeplabv3+ Deep Learning Model, Structural Durability & Health Monitoring, 18, 553, [https://doi.org/10.32604/sdhm.2024.050751](https://doi.org/10.32604/sdhm.2024.050751), 2024. [a](https://wes.copernicus.org/articles/11/1057/2026/#xref_paren.8)

Li, W., Zhao, W., and Du, Y.: Large-scale wind turbine blade operational condition monitoring based on UAV and improved YOLOv5 deep learning model, Mech. Syst. Signal Pr., 226, 112386, [https://doi.org/10.1016/j.ymssp.2025.112386](https://doi.org/10.1016/j.ymssp.2025.112386), 2025. [a](https://wes.copernicus.org/articles/11/1057/2026/#xref_paren.8)

Liu, H., Wang, Y., Zeng, T., Wang, H., Chan, S.-C., and Ran, L.: Wind turbine generator failure analysis and fault diagnosis: A review, IET Renewable Power Generation, 18, 3127–3148, [https://doi.org/10.1049/rpg2.13104](https://doi.org/10.1049/rpg2.13104), 2024. [a](https://wes.copernicus.org/articles/11/1057/2026/#xref_paren.4)

Machado, M.: iMOSS-Lab/rp-wedowind-challenge-ASCE-EMI: v1, Version v1, Zenodo \[code\], [https://doi.org/10.5281/zenodo.18940555](https://doi.org/10.5281/zenodo.18940555), 2026. [a](https://wes.copernicus.org/articles/11/1057/2026/#xref_paren.49)

Machado, M. and Dutkiewicz, M.: Wind turbine vibration management: An integrated analysis of existing solutions, products, and Open-source developments, Energy Reports, 11, 3756–3791, [https://doi.org/10.1016/j.egyr.2024.03.014](https://doi.org/10.1016/j.egyr.2024.03.014), 2024. [a](https://wes.copernicus.org/articles/11/1057/2026/#xref_paren.2)

Meyer, A.: Vibration Fault Diagnosis in Wind Turbines Based on Automated Feature Learning, Energies, 15, [https://doi.org/10.3390/en15041514](https://doi.org/10.3390/en15041514), 2022. [a](https://wes.copernicus.org/articles/11/1057/2026/#xref_text.37)

Milani, S., Leoni, J., Cacciola, S., Croce, A., and Tanelli, M.: A machine-learning-based approach for active monitoring of blade pitch misalignment in wind turbines, Wind Energ. Sci., 10, 497–510, [https://doi.org/10.5194/wes-10-497-2025](https://doi.org/10.5194/wes-10-497-2025), 2025. [a](https://wes.copernicus.org/articles/11/1057/2026/#xref_paren.31)

Morozovska, K., Bragone, F., Svensson, A. X., Shukla, D. A., and Hellstenius, E.: Trade-offs of wind power production: A study on the environmental implications of raw materials mining in the life cycle of wind turbines, J. Clean. Prod., 460, 142578, [https://doi.org/10.1016/j.jclepro.2024.142578](https://doi.org/10.1016/j.jclepro.2024.142578), 2024. [a](https://wes.copernicus.org/articles/11/1057/2026/#xref_paren.5)

Mousavi, Z., Varahram, S., Ettefagh, M. M., Sadeghi, M. H., Feng, W.-Q., and Bayat, M.: A digital twin-based framework for damage detection of a floating wind turbine structure under various loading conditions based on deep learning approach, Ocean Eng., 292, 116563, [https://doi.org/10.1016/j.oceaneng.2023.116563](https://doi.org/10.1016/j.oceaneng.2023.116563), 2024. [a](https://wes.copernicus.org/articles/11/1057/2026/#xref_paren.15)

Movsessian, A., Cava, D. G., and Tcherniak, D.: Interpretable Machine Learning in Damage Detection Using Shapley Additive Explanations, ASCE-ASME J. Risk and Uncert. in Engrg. Sys. Part B Mech. Engrg., 8, 021101, [https://doi.org/10.1115/1.4053304](https://doi.org/10.1115/1.4053304), 2022. [a](https://wes.copernicus.org/articles/11/1057/2026/#xref_text.20)

Nguyen, C. U., Huynh, T. C., and Kim, J. T.: Vibration-based damage detection in wind turbine towers using artificial neural networks, Structural Monitoring and Maintenance, 5, 507–519, [https://doi.org/10.12989/smm.2018.5.4.507](https://doi.org/10.12989/smm.2018.5.4.507), 2018. [a](https://wes.copernicus.org/articles/11/1057/2026/#xref_text.26)

Praveen, H. M., Sabareesh, G., Inturi, V., and Jaikanth, A.: Component level signal segmentation method for multi-component fault detection in a wind turbine gearbox, Measurement, 195, 111180, [https://doi.org/10.1016/j.measurement.2022.111180](https://doi.org/10.1016/j.measurement.2022.111180), 2022. [a](https://wes.copernicus.org/articles/11/1057/2026/#xref_text.35)

Regan, T., Beale, C., and Inalpolat, M.: Wind Turbine Blade Damage Detection Using Supervised Machine Learning Algorithms, J. Vib. Acoust., 139, 061010, [https://doi.org/10.1115/1.4036951](https://doi.org/10.1115/1.4036951), 2017. [a](https://wes.copernicus.org/articles/11/1057/2026/#xref_paren.9)

Ren, L. and Yong, B.: Wind Turbines Fault Classification Treatment Method, Symmetry, 14, [https://doi.org/10.3390/sym14040688](https://doi.org/10.3390/sym14040688), 2022. [a](https://wes.copernicus.org/articles/11/1057/2026/#xref_text.30)

Sharma, S. and Nava, V.: Condition monitoring of mooring systems for Floating Offshore Wind Turbines using Convolutional Neural Network framework coupled with Autoregressive coefficients, Ocean Eng., 302, 117650, [https://doi.org/10.1016/j.oceaneng.2024.117650](https://doi.org/10.1016/j.oceaneng.2024.117650), 2024. [a](https://wes.copernicus.org/articles/11/1057/2026/#xref_text.22)

Smarsly, K., Dragos, K., Chowdhury, S., and Wiggenbrock, J.: Machine learning algorithms for structural health monitoring. 8th European Workshop on Structural Health Monitoring (EWSHM 2016), 5–8 July 2016, Bilbao, Spain, e-Journal of Nondestructive Testing, 21, [https://www.ndt.net/?id=19828](https://www.ndt.net/?id=19828), 2016. [a](https://wes.copernicus.org/articles/11/1057/2026/#xref_paren.7)

Song, F., Han, Y., William Heath, A., and Hou, M.: Structural damage detection of floating offshore wind turbine blades based on Conv1d-GRU-MHA network, Eng. Fail. Anal., 166, 108896, [https://doi.org/10.1016/j.engfailanal.2024.108896](https://doi.org/10.1016/j.engfailanal.2024.108896), 2024. [a](https://wes.copernicus.org/articles/11/1057/2026/#xref_text.21)

Tang, X., Huang, W., Li, X., and Ma, G.: Prediction of mooring tension of floating offshore wind turbines by CNN-LSTM-ATT and Chebyshev polynomials, Ocean Eng., 331, 121327, [https://doi.org/10.1016/j.oceaneng.2025.121327](https://doi.org/10.1016/j.oceaneng.2025.121327), 2025. [a](https://wes.copernicus.org/articles/11/1057/2026/#xref_paren.12)

Thomas, D.: Unveiling Wind Turbine Failures Causes, Detection, and Prevention for Enhanced Reliability, Journal of Failure Analysis and Prevention, 24, 2051–2053, [https://doi.org/10.1007/s11668-024-02026-1](https://doi.org/10.1007/s11668-024-02026-1), 2024. [a](https://wes.copernicus.org/articles/11/1057/2026/#xref_paren.3)

Tsiapoki, S., Häckell, M. W., Grießmann, T., and Rolfes, R.: Damage and ice detection on wind turbine rotor blades using a three-tier modular structural health monitoring framework, Struct. Health Monit., 17, 1289–1312, [https://doi.org/10.1177/1475921717732730](https://doi.org/10.1177/1475921717732730), 2018. [a](https://wes.copernicus.org/articles/11/1057/2026/#xref_text.19)

Veers, P., Bottasso, C. L., Manuel, L., Naughton, J., Pao, L., Paquette, J., Robertson, A., Robinson, M., Ananthan, S., Barlas, T., Bianchini, A., Bredmose, H., Horcas, S. G., Keller, J., Madsen, H. A., Manwell, J., Moriarty, P., Nolet, S., and Rinker, J.: Grand challenges in the design, manufacture, and operation of future wind turbine systems, Wind Energ. Sci., 8, 1071–1131, [https://doi.org/10.5194/wes-8-1071-2023](https://doi.org/10.5194/wes-8-1071-2023), 2023.  [a](https://wes.copernicus.org/articles/11/1057/2026/#xref_paren.1)

Vidal, Y., Aquino, G., Pozo, F., and Gutiérrez-Arias, J. E. M.: Structural Health Monitoring for Jacket-Type Offshore Wind Turbines: Experimental Proof of Concept, Sensors, 20, [https://doi.org/10.3390/s20071835](https://doi.org/10.3390/s20071835), 2020. [a](https://wes.copernicus.org/articles/11/1057/2026/#xref_text.28)

Vives, J.: Vibration analysis for fault detection in wind turbines using machine learning techniques, Adv. Intell. Soft. Comp., 2, 1–12, [https://doi.org/10.1007/s43674-021-00029-1](https://doi.org/10.1007/s43674-021-00029-1), 2022. [a](https://wes.copernicus.org/articles/11/1057/2026/#xref_text.36)

Vives, J., Roses Albert, E., Quiles, E., Palací, J., and Fuster, T.: Vibration Analysis for Fault Detection of Wind Turbines by Combining Machine-Learning Techniques and 3D Scanning Laser, Genet. Res., 2022, [https://doi.org/10.1155/2022/2093086](https://doi.org/10.1155/2022/2093086), 2022. [a](https://wes.copernicus.org/articles/11/1057/2026/#xref_text.36)

Wang, S., Vidal, Y., and Pozo, F.: Recent advances in wind turbine condition monitoring using SCADA data: A state-of-the-art review, Reliab. Eng. Syst. Safe., 267, 111838, [https://doi.org/10.1016/j.ress.2025.111838](https://doi.org/10.1016/j.ress.2025.111838), 2026. [a](https://wes.copernicus.org/articles/11/1057/2026/#xref_text.48)

Zarrin, P. S., Martin, C., Langendoerfer, P., Wenger, C., and Diaz, M.: Vibration Analysis of a Wind Turbine Gearbox for Off-cloud Health Monitoring through Neuromorphic-computing, IECON Proceedings (Industrial Electronics Conference), 2021-October, [https://doi.org/10.1109/IECON48115.2021.9589879](https://doi.org/10.1109/IECON48115.2021.9589879), 2021. [a](https://wes.copernicus.org/articles/11/1057/2026/#xref_text.33)

Zhang, S., Wang, T., Worden, K., Sun, L., and Cross, E. J.: Canonical-correlation-based fast feature selection for structural health monitoring, Mech. Syst. Signal Pr., 223, 111895, [https://doi.org/10.1016/j.ymssp.2024.111895](https://doi.org/10.1016/j.ymssp.2024.111895), 2025. [a](https://wes.copernicus.org/articles/11/1057/2026/#xref_text.43), [b](https://wes.copernicus.org/articles/11/1057/2026/#xref_text.44)

Zhao, W., Li, W., and Du, Y.: Wind turbine blade rotational condition monitoring based on RBs-YOLO deep learning model, Mech. Syst. Signal Pr., 230, 112641, [https://doi.org/10.1016/j.ymssp.2025.112641](https://doi.org/10.1016/j.ymssp.2025.112641), 2025. [a](https://wes.copernicus.org/articles/11/1057/2026/#xref_paren.8)

[Articles](https://wes.copernicus.org/)

- [Abstract](https://wes.copernicus.org/articles/11/1057/2026/#abstract)
- [Introduction](https://wes.copernicus.org/articles/11/1057/2026/#section1)
- [Model description](https://wes.copernicus.org/articles/11/1057/2026/#section2)
- [Hybrid machine learning model](https://wes.copernicus.org/articles/11/1057/2026/#section3)
- [Results and discussion](https://wes.copernicus.org/articles/11/1057/2026/#section4)
- [Conclusions](https://wes.copernicus.org/articles/11/1057/2026/#section5)
- [Code availability](https://wes.copernicus.org/articles/11/1057/2026/#section6)
- [Data availability](https://wes.copernicus.org/articles/11/1057/2026/#section7)
- [Author contributions](https://wes.copernicus.org/articles/11/1057/2026/#section8)
- [Competing interests](https://wes.copernicus.org/articles/11/1057/2026/#section9)
- [Disclaimer](https://wes.copernicus.org/articles/11/1057/2026/#section10)
- [Acknowledgements](https://wes.copernicus.org/articles/11/1057/2026/#section11)
- [Financial support](https://wes.copernicus.org/articles/11/1057/2026/#section12)
- [Review statement](https://wes.copernicus.org/articles/11/1057/2026/#section13)
- [References](https://wes.copernicus.org/articles/11/1057/2026/#section14)

Short summary

We have developed a method using artificial intelligence to detect and classify faults in wind...

Similar articles

Gettemy et al.

Huang et al.

Kestel et al.

[^1]: **Algorithm 1** Hybrid ML model for Aventa wind turbine failure classification.

1: **Data acquisition:** Receive time-domain structural response from accelerometer sensors and environmental conditions from the SCADA.

2: **Data processing:** Involves correcting raw data by checking for missing values and applying signal processing techniques.

3: **Feature extraction, normalization, and grouping:** Fifteen formulations are employed to extract features from the time-domain signal, which is then grouped by similarity (see Sect. [2.3](https://wes.copernicus.org/articles/11/1057/2026/#Ch1.S2.SS3)).

4: **Pattern recognition, labelling, and clustering:** Use the *k* -means unsupervised algorithm to cluster the data: $J = \sum_{i = 1}^{n} min_{k} \left(\left(x_{i} - \left(\overset{\overline}{x}\right)_{k}\right)^{2}\right)$

5: **Feature and sensor selection:** This is performed via canonical-correlation-based selection and final dataset organization.

6: **Data splitting and ML classification:** Split the dataset into training and testing as listed in Table [4](https://wes.copernicus.org/articles/11/1057/2026/#Ch1.T4). Further, apply the ML algorithms (SVM, K-NN, RF, NB, DT, and XGBoost) for failure identification and classification.

7: **Model evaluation:** Calculate the performance of the ML classifiers (Cross-validation, accuracy, precision, recall, and the F1-score), identification of the best ML model(s), and generation of the confusion matrix.

**Final decision:** This concerns information about failure state based on classification algorithm outcomes.

[^2]: [![https://wes.copernicus.org/articles/11/1057/2026/wes-11-1057-2026-f01](https://wes.copernicus.org/articles/11/1057/2026/wes-11-1057-2026-f01-thumb.png)](https://wes.copernicus.org/articles/11/1057/2026/wes-11-1057-2026-f01-web.png)

**Figure 1** Pipeline of the hybrid machine learning model for fault classification on the Aventa 6.7 kW wind turbine.

[Download](https://wes.copernicus.org/articles/11/1057/2026/wes-11-1057-2026-f01.png)

## 2.1 Data processing, signal, and sensor analysis

The wind turbine monitored in this study is the Aventa AV-7 model, manufactured by Aventa AG (Switzerland) and commissioned by ETH. This turbine has a rated power of 6.7 kW and operates using a belt-driven generator coupled with a frequency converter and a variable-speed drive. It begins generating power at a wind speed of 2 m s <sup>−1</sup> and has a cut-off speed of 14 m s <sup>−1</sup>. The rotor has a diameter of 12.8 m with three blades and is mounted at a hub height of 18 m. The maximum rotational speed reaches 63 rpm. Turbine control is managed through a variable-speed and variable-pitch mechanism. The turbine is installed in Taggenberg, Switzerland (coordinates: 47°31 <sup>′</sup> 12.2 <sup>′′</sup>  N, 8°40 <sup>′</sup> 55.7 <sup>′′</sup>  E). Instrumentation and data acquisition were provided in [Chatzi et al.](https://wes.copernicus.org/articles/11/1057/2026/#bib1.bibx13) ([2023](https://wes.copernicus.org/articles/11/1057/2026/#bib1.bibx13)) and include 14 accelerometers strategically placed along the tower, on the nacelle main frame, the main bearing, and the generator, as shown in Fig. [2](https://wes.copernicus.org/articles/11/1057/2026/#Ch1.F2). Additionally, two full-bridge strain gauges are mounted at the tower base to measure fore-aft and side-to-side strain, which can be converted into bending moments. Acceleration and strain signals are sampled at 200 Hz. Environmental measurements, including temperature and humidity, are collected at the tower base at a sampling rate of 1 Hz. Operational performance data (SCADA), including wind speed, nacelle yaw orientation, rotor RPM, power output, and turbine status, are recorded at 10 Hz. To ensure data quality and enhance the reliability of fault detection, a comprehensive supervised data preprocessing was implemented. This included supervised sensor analysis, outlier removal, signal segmentation, detrending, feature extraction, normalization, and similar feature identification and grouping.

[![https://wes.copernicus.org/articles/11/1057/2026/wes-11-1057-2026-f02](https://wes.copernicus.org/articles/11/1057/2026/wes-11-1057-2026-f02-thumb.png)](https://wes.copernicus.org/articles/11/1057/2026/wes-11-1057-2026-f02-web.png)

**Figure 2** Schematic representation of the turbine sensor channel and location ([Chatzi et al.](https://wes.copernicus.org/articles/11/1057/2026/#bib1.bibx13), [2023](https://wes.copernicus.org/articles/11/1057/2026/#bib1.bibx13)). SCADA data and accelerometers marked in orange, blue, and yellow colours are adopted in the monitoring **(a)**. Temporal signal data of the turbine's NO and operation with failures **(b)**: top: sensor GEN NO-FC, NO-RI, and NO-AI placed from left to right, respectively; middle: sensor MSB NO-FC, NO-RI, and NO-AI; and bottom: sensor NMF NO-FC, NO-RI, and NO-AI.

[Download](https://wes.copernicus.org/articles/11/1057/2026/wes-11-1057-2026-f02.png)

**Table 1** Information on SCADA data and accelerometers used in the monitoring, with the respective sensor channel and location.

[![](https://wes.copernicus.org/articles/11/1057/2026/wes-11-1057-2026-t01-thumb.png)](https://wes.copernicus.org/articles/11/1057/2026/wes-11-1057-2026-t01.png)

[Download Print Version](https://wes.copernicus.org/articles/11/1057/2026/wes-11-1057-2026-t01.png) | [Download XLSX](https://wes.copernicus.org/articles/11/1057/2026/wes-11-1057-2026-t01.xlsx)

The data preprocessing stage begins by analysing the sensors' physics and evaluating each sensor's contribution to failure identification. The pre-established failures are the rotor icing event (RI), the flexible coupling of the linear drive of the collective pitch system (FC), and aerodynamic imbalance on one blade (AI). The Aventa dataset provides three-axis acceleration signals. Table [1](https://wes.copernicus.org/articles/11/1057/2026/#Ch1.T1) lists the SCADA data and accelerometers used for monitoring, along with their respective sensor channels and locations. The *x* axis captures side-to-side turbine motion, and the *y* axis captures fore-aft turbine motion. Figure [2](https://wes.copernicus.org/articles/11/1057/2026/#Ch1.F2) a illustrates the sensor locations within the turbine. Aside from the SCADA data (temperature and wind velocity), accelerometers marked in orange, blue, and yellow are used for monitoring. Specifically, three accelerometers are located in the nacelle, GEN *\_* ACC (orange), NMF *\_* ACC (blue), and MSB *\_* ACC (yellow); and one is located at the tower top, F5 *\_* ACC. The sensors record signals under the different operational conditions, including normal operation (NO). Figure [2](https://wes.copernicus.org/articles/11/1057/2026/#Ch1.F2) also presents the raw temporal data available in the dataset. In the acceleration graphs, black lines indicate normal turbine operation, whereas coloured lines represent various failure conditions. To ensure consistent comparisons, all signals were selected from the same day, minimizing the influence of changing environmental conditions.

The top row of graphs shows the *x* axis response from the generator-mounted sensor (GEN), comparing NO with failures FC, RI, and AI, from left to right. The middle row displays the *x* axis response from the main shaft bearing sensor (MSB), and the bottom row shows the same for the nacelle main frame sensor (NMF), following the same failure comparison pattern. Both *x* and *y* axis signals were analysed, revealing consistent trends: FC failures led to a pronounced amplitude reduction, whereas RI and AI failures resulted in only minor amplitude changes. These variations may fluctuate daily due to environmental conditions. To ensure effective fault detection, data from accelerometer sensors placed at the tower top, nacelle, main shaft bearing, and generator were used in the model, considering their sensitivity to structural, mechanical, and aerodynamic failures.

## 2.2 Dataset

During data analysis, duplicate files were identified, prompting a data redistribution strategy to eliminate redundancies and streamline the process. The data were categorized and colour-coded by operational conditions and events, making patterns – such as seasonality, frequency, and duration – more apparent and visually accessible. These cleaning and reorganization steps ensure that the same data are not reused across different turbine operations, thereby reducing the risk of misclassification and misinterpretation during monitoring.

[![https://wes.copernicus.org/articles/11/1057/2026/wes-11-1057-2026-f03](https://wes.copernicus.org/articles/11/1057/2026/wes-11-1057-2026-f03-thumb.png)](https://wes.copernicus.org/articles/11/1057/2026/wes-11-1057-2026-f03-web.png)

**Figure 3** The feature dataset volume over the monitoring timeline categorized by yellow indicates RI, blue denotes NO, purple corresponds to AI, and orange represents the FC condition **(a)** (top). Wind speed boxplot **(a)** (middle), and mean temperature (**(a)** bottom). Boxplot of L05 sensor feature by wind speed variation **(b)** and feature by temperature variation **(c)**.

[Download](https://wes.copernicus.org/articles/11/1057/2026/wes-11-1057-2026-f03-high-res.png)

Feature extraction was performed after this reorganization. Aside from the accelerometer sensors, the supervisory control and data acquisition (SCADA) data include the temperature, wind speed, humidity, and power output. Temperature, wind speed, and acceleration responses are used for monitoring. Figure [3](https://wes.copernicus.org/articles/11/1057/2026/#Ch1.F3) a shows the maximum values of the temporal spectrum for each operational condition mapped over the monitoring timeline. Each condition is colour-coded for clarity: yellow for RI, blue for NO, purple for AI, and orange for flexible FC. Events are plotted along the horizontal axis to highlight their temporal distribution. The timeline begins with a NO sample, followed by a pitch drive coupling failure recorded on 16 February 2022, which required replacement. From April to November 2022, the turbine operated normally, during which AI was intentionally simulated using roughness tape on the blades. Additionally, naturally occurring RI events were observed between December 2022 and February 2023. Wind speed fluctuates throughout the monitoring period, as indicated by the boxplot, which displays the minimum, maximum, median, and first and third quartiles of the wind speed data. Meanwhile, ambient temperature ranges from −2 to 26 °C throughout the year (see Fig. [3](https://wes.copernicus.org/articles/11/1057/2026/#Ch1.F3) c).

Both environmental conditions – wind speed and temperature – significantly influence the dynamic response of the wind turbine over time. Figure [3](https://wes.copernicus.org/articles/11/1057/2026/#Ch1.F3) b–c present boxplots showing the feature values corrected by wind speed and temperature, respectively. This analysis focuses on the RMS value of sensor NMF, selected for its highest-scoring features and well-defined failure patterns, which represent the general behaviour of the features. When correlating feature values with wind speed, the FC and AI conditions exhibit the greatest sensitivity to increasing wind speeds, though with relatively low dispersion. Conversely, RI, NO, and FC show higher maximum, minimum, and quartile values at lower wind speeds. Regarding temperature, rising temperatures primarily affect NO and AI conditions, whereas lower temperatures have a greater impact on FC and RI. These findings underscore the importance of incorporating environmental variables into the monitoring framework to improve the robustness and accuracy of fault classification. The SCADA data in the general dataset are considered the mean temperature and mean wind speed, both acquired over the 24 h of the respective day.

## 2.3 Feature extraction, normalization, and dataset organization

Feature selection involves choosing a subset of variables from the original dataset. This step transforms the spectrum data into new variables to create a refined dataset ([Bishop](https://wes.copernicus.org/articles/11/1057/2026/#bib1.bibx11), [2006](https://wes.copernicus.org/articles/11/1057/2026/#bib1.bibx11)). Fifteen features are formulated using the time-domain signal ([Knittel et al.](https://wes.copernicus.org/articles/11/1057/2026/#bib1.bibx32), [2019](https://wes.copernicus.org/articles/11/1057/2026/#bib1.bibx32); [Barreto et al.](https://wes.copernicus.org/articles/11/1057/2026/#bib1.bibx10), [2021](https://wes.copernicus.org/articles/11/1057/2026/#bib1.bibx10); [Ashkarkalaei et al.](https://wes.copernicus.org/articles/11/1057/2026/#bib1.bibx6), [2025](https://wes.copernicus.org/articles/11/1057/2026/#bib1.bibx6) [a](https://wes.copernicus.org/articles/11/1057/2026/#bib1.bibx6)), as presented in Table [2](https://wes.copernicus.org/articles/11/1057/2026/#Ch1.T2), where *x* is the temporal spectrum signal and *p* is the sampling points value.

**Table 2** Temporal and statistical formulation used for feature extraction.

[![](https://wes.copernicus.org/articles/11/1057/2026/wes-11-1057-2026-t02-thumb.png)](https://wes.copernicus.org/articles/11/1057/2026/wes-11-1057-2026-t02.png)

[Download Print Version](https://wes.copernicus.org/articles/11/1057/2026/wes-11-1057-2026-t02.png) | [Download XLSX](https://wes.copernicus.org/articles/11/1057/2026/wes-11-1057-2026-t02.xlsx)

Temporal features are extracted from a signal's frequency or time content, such as maximum, minimum, amplitude range, energy, energy centre, skewness, signal rate, and RMS. It captures how the signal's energy is distributed over time. Statistical features, in turn, are computed from the signal's time-domain values, including the median, mean, variance, skewness, kurtosis, higher-order moments, and standard deviation, which characterize the overall distribution and variability of the signal. Together, these features are compiled, analysed, and evaluated for their similarity and sensitivity to the system's dynamic behaviour.

Despite feature refinement and grouping, the remaining features still pose a challenge due to their minimal amplitude variation, often differing by only a few digits. Such small variations can hinder accurate machine learning classification. To address this issue, the proposed relative change damage index incorporates a normalization step based on the relative change of each feature, defined as

$$
\begin{aligned}
(\text{1a}) \Delta_{f} = max \left(\mathbf{X}_{i}\right) - \mathbf{X}_{i} \\ (\text{1b}) \text{RC} = \frac{\Delta_{f}}{max \left(\Delta_{f}\right)} ,
\end{aligned}
$$

where **X** is a table containing the selected features and Δ <sub>f</sub> measures each feature's deviation from its maximum value within the selected feature set to each feature vector point (**X** <sub><i>i</i></sub>). The normalization factor RC rescales these deviations to the \[0, 1\] interval. This linear transformation preserves the original ordering and proportionality of the data, ensuring that the intrinsic dynamic pattern is maintained. At the same time, it amplifies subtle differences that would otherwise be masked by small numerical variations, thereby enhancing the sensitivity of the features for fault detection and classification. Hence, the RC normalization converts the data into dimensionless features that, prior to normalization, differed only slightly (e.g. 3.280 vs 3.286), rendering these differences numerically negligible for machine learning models. Thus, the proposed approach amplifies these small variations while preserving the intrinsic dynamic pattern. Features with values close to unity correspond to undamaged conditions, whereas values approaching zero indicate faults. Hence, the method enhances fault sensitivity and enables consistent comparison across features of different magnitudes, making the damage feature more sensitive to anomalies under varying operating states.

[![https://wes.copernicus.org/articles/11/1057/2026/wes-11-1057-2026-f04](https://wes.copernicus.org/articles/11/1057/2026/wes-11-1057-2026-f04-thumb.png)](https://wes.copernicus.org/articles/11/1057/2026/wes-11-1057-2026-f04-web.png)

**Figure 4** **(a)** Non-normalized features grouped by similarity under different operating conditions: NO – blue, FC – orange, RI – yellow, and AI – purple. **(b)** Demonstration of the scaling and normalization on the Amp feature related to Eq. ([1](https://wes.copernicus.org/articles/11/1057/2026/#Ch1.E1)). Scaled and normalized features grouped by similarity under different conditions **(c)**.

[Download](https://wes.copernicus.org/articles/11/1057/2026/wes-11-1057-2026-f04.png)

The relative change normalization provides a theoretical foundation based on relative scaling and dimensionless feature representation. Figure [4](https://wes.copernicus.org/articles/11/1057/2026/#Ch1.F4) a–c illustrates the process: (a) the non-normalized features, (b) the scaling and normalization applied to the Amp feature (extended to all others), and (c) the normalized features obtained using the proposed relative change technique. Features such as energy, kurtosis, higher-order moments, and Shannon entropy exhibited low sensitivity to failures and were excluded during normalization and analysis. This first supervised analysis revealed two feature groups with similar behaviour. Group 1 consists of the RMS and median (Fig. [4](https://wes.copernicus.org/articles/11/1057/2026/#Ch1.F4) c, top), while Group 2 comprises the maximum, minimum, amplitude range, variance, energy centre, and signal rate (Fig. [4](https://wes.copernicus.org/articles/11/1057/2026/#Ch1.F4) c, bottom). The formation of two feature groups indicates a high degree of correlation within each group, with RMS and median primarily capturing the signal's central tendency. In contrast, the features of Group 2 describe its variability and extremes. Therefore, using all features would introduce redundancy, increase computational cost, and risk overfitting due to the curse of dimensionality. Selecting only representative features from each group ensures that the classifier retains the essential discriminatory information while improving efficiency and generalization.

From the two correlated feature groups, four representative features (RMS, maximum, variance, and amplitude range) were selected to compose the global dataset. Those four features were chosen over the other in their respective group due to near-equivalence, thus avoiding redundancy. The initial global dataset, therefore, consisted of the four selected features extracted from each sensor axis, resulting in a structure of measurement\_rows × 48 columns, plus the SCADA data, as detailed in Table [1](https://wes.copernicus.org/articles/11/1057/2026/#Ch1.T1). However, including all these features may appear arbitrary and degrade model performance due to their high similarity. To refine the global dataset, a canonical correlation analysis was applied to identify the most sensitive features for each sensor, accounting for all axes simultaneously within the sensor group. The highest feature correlation scores were selected, reducing the dataset to four representative features plus SCADA. This process yielded the final datasets: the binary classification dataset has six columns (four features plus SCADA), and the multi-class dataset has nine columns (selected features plus SCADA). Identifying the most informative sensor is also relevant, as it indicates which sensor contributes most to classification accuracy and provides resilience in the event of sensor loss. To validate this study, the most sensitive feature from the best-performing sensor was removed in subsequent tests, thereby demonstrating the robustness and consistency of the proposed feature selection strategy. Feature and sensor selection are detailed in Sect. [2.1](https://wes.copernicus.org/articles/11/1057/2026/#Ch1.S2.SS1).

### Structured final datasets

The final refined dataset organization is a crucial step for enabling machine learning algorithms to accurately classify operational failures. The deployed dataset exhibits a multimodal nature, integrating structural, temperature, and wind velocity information. The structural data are directly acquired from the accelerometers, which capture the system's physical response and potential failure signatures. In contrast, temperature and wind speed data are obtained from the SCADA system and represent indirect but relevant variables that influence the dynamic behaviour measured by the accelerometers. However, they do not directly describe the damage dynamics. The final dataset is organized into four configurations, which are evaluated. Their relevance is demonstrated in Sect. [4](https://wes.copernicus.org/articles/11/1057/2026/#Ch1.S4), yielding the following:

- *Fe-kms-Sc*. Dataset composed of the selected features (Fe) extracted from the accelerometer time signals, followed by the SCADA data (Sc) and label defined by the *k* -means clustering (kms),
- *Fe-Sc-kms*. Dataset including the selected features, the SCADA data, and the corresponding *k* -means labels,
- *Fe-kms*. Dataset including the selected features and the *k* -means labels, without incorporating the SCADA information,
- *Fe-kms-LoseSensor*. Dataset including the selected features excluding those obtained from the most sensitive sensor identified by the Fast CCA method, together with the *k* -means labels and SCADA data. This configuration simulates the loss of the most sensitive sensor in each analysis scenario.

The *k* -means labelling of the datasets *Fe-kms-Sc* and *Fe-kms-LoseSensor* is applied exclusively to the features that contain the most relevant physical information about the damage. The SCADA data are then organized by the corresponding day and hour for each feature sample. This ensures that the SCADA records follow the same row reordering imposed by the *k* -means clustering, while preserving the correct temporal (day and hour) correspondence between the SCADA measurements and the related accelerometer data.

[^3]: [![https://wes.copernicus.org/articles/11/1057/2026/wes-11-1057-2026-f02](https://wes.copernicus.org/articles/11/1057/2026/wes-11-1057-2026-f02-thumb.png)](https://wes.copernicus.org/articles/11/1057/2026/wes-11-1057-2026-f02-web.png)

**Figure 2** Schematic representation of the turbine sensor channel and location ([Chatzi et al.](https://wes.copernicus.org/articles/11/1057/2026/#bib1.bibx13), [2023](https://wes.copernicus.org/articles/11/1057/2026/#bib1.bibx13)). SCADA data and accelerometers marked in orange, blue, and yellow colours are adopted in the monitoring **(a)**. Temporal signal data of the turbine's NO and operation with failures **(b)**: top: sensor GEN NO-FC, NO-RI, and NO-AI placed from left to right, respectively; middle: sensor MSB NO-FC, NO-RI, and NO-AI; and bottom: sensor NMF NO-FC, NO-RI, and NO-AI.  

[Download](https://wes.copernicus.org/articles/11/1057/2026/wes-11-1057-2026-f02.png)

[^4]: **Table 1** Information on SCADA data and accelerometers used in the monitoring, with the respective sensor channel and location. 

[![](https://wes.copernicus.org/articles/11/1057/2026/wes-11-1057-2026-t01-thumb.png)](https://wes.copernicus.org/articles/11/1057/2026/wes-11-1057-2026-t01.png)

[Download Print Version](https://wes.copernicus.org/articles/11/1057/2026/wes-11-1057-2026-t01.png) | [Download XLSX](https://wes.copernicus.org/articles/11/1057/2026/wes-11-1057-2026-t01.xlsx)

[^5]: [![https://wes.copernicus.org/articles/11/1057/2026/wes-11-1057-2026-f03](https://wes.copernicus.org/articles/11/1057/2026/wes-11-1057-2026-f03-thumb.png)](https://wes.copernicus.org/articles/11/1057/2026/wes-11-1057-2026-f03-web.png)

**Figure 3** The feature dataset volume over the monitoring timeline categorized by yellow indicates RI, blue denotes NO, purple corresponds to AI, and orange represents the FC condition **(a)** (top). Wind speed boxplot **(a)** (middle), and mean temperature (**(a)** bottom). Boxplot of L05 sensor feature by wind speed variation **(b)** and feature by temperature variation **(c)**.  

[Download](https://wes.copernicus.org/articles/11/1057/2026/wes-11-1057-2026-f03-high-res.png)

[^6]: **Table 2** Temporal and statistical formulation used for feature extraction.

[![](https://wes.copernicus.org/articles/11/1057/2026/wes-11-1057-2026-t02-thumb.png)](https://wes.copernicus.org/articles/11/1057/2026/wes-11-1057-2026-t02.png)

[Download Print Version](https://wes.copernicus.org/articles/11/1057/2026/wes-11-1057-2026-t02.png) | [Download XLSX](https://wes.copernicus.org/articles/11/1057/2026/wes-11-1057-2026-t02.xlsx)

[^7]: $$
\begin{aligned}
(\text{1a}) \Delta_{f} = max \left(\mathbf{X}_{i}\right) - \mathbf{X}_{i} \\ (\text{1b}) \text{RC} = \frac{\Delta_{f}}{max \left(\Delta_{f}\right)} ,
\end{aligned}
$$

[^8]: [![https://wes.copernicus.org/articles/11/1057/2026/wes-11-1057-2026-f04](https://wes.copernicus.org/articles/11/1057/2026/wes-11-1057-2026-f04-thumb.png)](https://wes.copernicus.org/articles/11/1057/2026/wes-11-1057-2026-f04-web.png)

**Figure 4** **(a)** Non-normalized features grouped by similarity under different operating conditions: NO – blue, FC – orange, RI – yellow, and AI – purple. **(b)** Demonstration of the scaling and normalization on the Amp feature related to Eq. ([1](https://wes.copernicus.org/articles/11/1057/2026/#Ch1.E1)). Scaled and normalized features grouped by similarity under different conditions **(c)**.  

[Download](https://wes.copernicus.org/articles/11/1057/2026/wes-11-1057-2026-f04.png)

[^9]: **Table 3** *k* -means clustering identification for each sensor related to the failure associated with the silhouette coefficient and Davies–Bouldin index performance metrics.

[![](https://wes.copernicus.org/articles/11/1057/2026/wes-11-1057-2026-t03-thumb.png)](https://wes.copernicus.org/articles/11/1057/2026/wes-11-1057-2026-t03.png)

[Download Print Version](https://wes.copernicus.org/articles/11/1057/2026/wes-11-1057-2026-t03.png) | [Download XLSX](https://wes.copernicus.org/articles/11/1057/2026/wes-11-1057-2026-t03.xlsx)

[^10]: **Table 4** Explicit description of the datasets used for training, validation, and testing. 

[![](https://wes.copernicus.org/articles/11/1057/2026/wes-11-1057-2026-t04-thumb.png)](https://wes.copernicus.org/articles/11/1057/2026/wes-11-1057-2026-t04.png)

[Download Print Version](https://wes.copernicus.org/articles/11/1057/2026/wes-11-1057-2026-t04.png) | [Download XLSX](https://wes.copernicus.org/articles/11/1057/2026/wes-11-1057-2026-t04.xlsx)

[^11]: **Algorithm 2** Pseudocode for the feature and sensor selection with canonical correlation. 

**Input:** $\mathbf{X} \in \mathbb{R}^{N \times n}$ *Candidate feature matrix*

**Input:** $\mathbf{Y} \in \mathbb{R}^{N \times m}$ *Target multi-label matrix*

**Output:** $\mathbf{d} \in \mathbb{R}^{1 \times \mathcal{T}}$, where $\mathbf{d} = \left(d_{1} , d_{2} , \ldots , d_{t}\right)$ *Index of the feature with the highest ranking score*

**Output:** $\mathbf{q} \in \mathbb{R}^{1 \times s}$, where $\mathbf{q} = \left(q_{1} , q_{2} , \ldots , q_{s}\right)$ *Index of the feature with the highest ranking score associated with the sensor*

1:

𝒯∈ *N* *Number of features to be selected*

2:

s∈S *Number of sensors*

3:

**X** <sub>s</sub> ←0 *Candidate feature matrix coating the best feature(s) of each sensor. The threshold score is* ≥0.6

4:

**for** *j* ←1 to s **do**

5:

$\mathbf{X}_{C} \leftarrow \left[\right. \mathbf{X} - \text{mean} \left(\mathbf{X}\right)$\], $\mathbf{Y}_{C} \leftarrow \left[\mathbf{Y} - \text{mean} \left(\mathbf{Y}\right)\right]$

6:

**if** use *η* -cosine **then**

7:

$$
\left[\mathbf{U} , \mathbf{S} , \mathbf{V}_{h}^{\top}\right] \leftarrow \text{svd} \left(\left[\mathbf{X}_{C} \mid \mathbf{Y}_{C}\right]\right)
$$

8:

$$
\left[\right. \mathbf{X}_{C} \left]\right._{U} \mid \left[\right. \mathbf{Y}_{C} \left]\right._{U} \leftarrow \mathbf{SV}_{h}^{\top}
$$

9:

**end** **if**

10:

$R_{i}^{2} \leftarrow 0$ for $i = 1 , \ldots , n$ *Feature ranking scores*

11:

*d* <sub><i>i</i></sub> ←0 for $i = 1 , \ldots , t$ *Output indices vector, where* *t* ∈ *N* *is the number of features to be selected*

12:

**procedure** FASTCAN X, Y, t, tol, alg *Function described in [Zhang et al.](https://wes.copernicus.org/articles/11/1057/2026/#bib1.bibx65) ([2025](https://wes.copernicus.org/articles/11/1057/2026/#bib1.bibx65))*

13:

$$
d \leftarrow arg max_{j} R_{j}^{2}
$$

14:

**return** **d**

15:

$\mathbf{X}_{s} \leftarrow \mathbf{X} \left[: , max \left(\mathbf{d}\right)\right]$ *Highest score feature*

16:

**end** **for**

17:

**procedure** FASTCAN **X** <sub>s</sub>, Y, s, tol, alg

18:

$$
\text{q} \leftarrow arg max_{j} R_{j}^{2}
$$

19:

**return** q

[^12]: 4 Results and discussion

[^13]: **Table 5** Description of the sensitive feature of each sensor (X <sub>s</sub>) and an indication of the most sensitive sensor of each failure case. 

[![](https://wes.copernicus.org/articles/11/1057/2026/wes-11-1057-2026-t05-thumb.png)](https://wes.copernicus.org/articles/11/1057/2026/wes-11-1057-2026-t05.png)

[Download Print Version](https://wes.copernicus.org/articles/11/1057/2026/wes-11-1057-2026-t05.png) | [Download XLSX](https://wes.copernicus.org/articles/11/1057/2026/wes-11-1057-2026-t05.xlsx)

[^14]: [![https://wes.copernicus.org/articles/11/1057/2026/wes-11-1057-2026-f05](https://wes.copernicus.org/articles/11/1057/2026/wes-11-1057-2026-f05-thumb.png)](https://wes.copernicus.org/articles/11/1057/2026/wes-11-1057-2026-f05-web.png)

**Figure 5** CCA feature score and dispersion diagrams of the highest-scoring feature for the NO-FC failure: **(a)** sensor MSH, **(b)** sensor L05 (1 and 2), **(c)** sensor GEN, and **(d)** sensor NMF (1 and 2). 

[Download](https://wes.copernicus.org/articles/11/1057/2026/wes-11-1057-2026-f05.png)

[^15]: [![https://wes.copernicus.org/articles/11/1057/2026/wes-11-1057-2026-f06](https://wes.copernicus.org/articles/11/1057/2026/wes-11-1057-2026-f06-thumb.png)](https://wes.copernicus.org/articles/11/1057/2026/wes-11-1057-2026-f06-web.png)

**Figure 6** CCA feature score and dispersion diagrams of the highest-scoring feature for the NO-RI failure: **(a)** sensor MSH, **(b)** sensor L05 (1 and 2), **(c)** sensor GEN, and **(d)** sensor NMF (1 and 2). 

[Download](https://wes.copernicus.org/articles/11/1057/2026/wes-11-1057-2026-f06.png)

[^16]: [![https://wes.copernicus.org/articles/11/1057/2026/wes-11-1057-2026-f07](https://wes.copernicus.org/articles/11/1057/2026/wes-11-1057-2026-f07-thumb.png)](https://wes.copernicus.org/articles/11/1057/2026/wes-11-1057-2026-f07-web.png)

**Figure 7** CCA feature score and dispersion diagrams of the highest-scoring feature for the NO-AI failure: **(a)** sensor MSH, **(b)** sensor L05 (1 and 2), **(c)** sensor GEN, and **(d)** sensor NMF (1 and 2).  

[Download](https://wes.copernicus.org/articles/11/1057/2026/wes-11-1057-2026-f07.png)

[^17]: [![https://wes.copernicus.org/articles/11/1057/2026/wes-11-1057-2026-f08](https://wes.copernicus.org/articles/11/1057/2026/wes-11-1057-2026-f08-thumb.png)](https://wes.copernicus.org/articles/11/1057/2026/wes-11-1057-2026-f08-web.png)

**Figure 8** Sensor score based on the top-performing features of each operational condition: **(a)** NO-FC, **(b)** NO-AI, **(c)** NO-RI, and **(d)** multi-class.   

[Download](https://wes.copernicus.org/articles/11/1057/2026/wes-11-1057-2026-f08.png)

[^18]: [![https://wes.copernicus.org/articles/11/1057/2026/wes-11-1057-2026-f09](https://wes.copernicus.org/articles/11/1057/2026/wes-11-1057-2026-f09-thumb.png)](https://wes.copernicus.org/articles/11/1057/2026/wes-11-1057-2026-f09-web.png)

**Figure 9** CCA feature score and dispersion diagrams of the highest-scoring feature: **(a)** sensor MSH, **(b)** sensor L05 (1 and 2), **(c)** sensor GEN, and **(d)** sensor NMF (1 and 2).  

[Download](https://wes.copernicus.org/articles/11/1057/2026/wes-11-1057-2026-f09.png)

[^19]: [![https://wes.copernicus.org/articles/11/1057/2026/wes-11-1057-2026-f10](https://wes.copernicus.org/articles/11/1057/2026/wes-11-1057-2026-f10-thumb.png)](https://wes.copernicus.org/articles/11/1057/2026/wes-11-1057-2026-f10-web.png)

**Figure 10** Comparison of the metrics (accuracy, F1-score, precision, recall, and cross-validation) for the six ML algorithms and each arranged final dataset. **(a)** Binary NO-FC, **(b)** binary NO-AI, **(c)** binary NO-RI, and **(d)** multi-class failure study cases.   

[Download](https://wes.copernicus.org/articles/11/1057/2026/wes-11-1057-2026-f10.png)

[^20]: [![https://wes.copernicus.org/articles/11/1057/2026/wes-11-1057-2026-f11](https://wes.copernicus.org/articles/11/1057/2026/wes-11-1057-2026-f11-thumb.png)](https://wes.copernicus.org/articles/11/1057/2026/wes-11-1057-2026-f11-web.png)

**Figure 11** Feature score of the *Fe-Sc-kms* dataset for **(a)** NO-FC, **(b)** NO-RI, **(c)** NO-AI, and **(d)** multi-class.

[Download](https://wes.copernicus.org/articles/11/1057/2026/wes-11-1057-2026-f11.png)

[^21]: [![https://wes.copernicus.org/articles/11/1057/2026/wes-11-1057-2026-f12](https://wes.copernicus.org/articles/11/1057/2026/wes-11-1057-2026-f12-thumb.png)](https://wes.copernicus.org/articles/11/1057/2026/wes-11-1057-2026-f12-web.png)

**Figure 12** Confusion matrix of binary operational classification for **(a)** NO-FC, **(b)** NO-RI, **(c)** NO-AI, and **(d)** multi-classification. The dataset assumes the best features plus SCADA data (temperature and wind speed) in each analysis. 

[Download](https://wes.copernicus.org/articles/11/1057/2026/wes-11-1057-2026-f12.png)

[^22]: Amin, A., Bibo, A., Panyam, M., and Tallapragada, P.: Vibration based fault diagnostics in a wind turbine planetary gearbox using machine learning, Wind Engineering, 47, 175–189, [https://doi.org/10.1177/0309524X221123968](https://doi.org/10.1177/0309524X221123968), 2023. [a](https://wes.copernicus.org/articles/11/1057/2026/#xref_text.38)

[^23]: Ángel Encalada-Dávila, Vidal, Y., and Tutivén, C.: Strain virtual sensor for offshore wind turbine jacket supports: A time series transformer approach validated with Alpha Ventus wind farm data, Mech. Syst. Signal Pr., 231, 112653, [https://doi.org/10.1016/j.ymssp.2025.112653](https://doi.org/10.1016/j.ymssp.2025.112653), 2025. [a](https://wes.copernicus.org/articles/11/1057/2026/#xref_paren.14)

[^24]: Antoniadou, I., Dervilis, N., Barthorpe, R. J., Manson, G., and Worden, K.: Advanced tools for damage detection in wind turbines, Key Engineering Materials, 569–570, 547–554, [https://doi.org/10.4028/www.scientific.net/KEM.569-570.547](https://doi.org/10.4028/www.scientific.net/KEM.569-570.547), 2013. [a](https://wes.copernicus.org/articles/11/1057/2026/#xref_paren.16)

[^25]: Antoniadou, I., Dervilis, N., Papatheou, E., Maguire, A. E., and Worden, K.: Aspects of structural health and condition monitoring of offshore wind turbines, Philos. T. R. Soc. A, 373, [https://doi.org/10.1098/rsta.2014.0075](https://doi.org/10.1098/rsta.2014.0075), 2015a. [a](https://wes.copernicus.org/articles/11/1057/2026/#xref_paren.16)

[^26]: Antoniadou, I., Dervilis, N., Papatheou, E., Maguire, A. E., and Worden, K.: Aspects of structural health and condition monitoring of offshore wind turbines, Philos. T. R. Soc. A, 373, 20140075, [https://doi.org/10.1098/rsta.2014.0075](https://doi.org/10.1098/rsta.2014.0075), 2015b. [a](https://wes.copernicus.org/articles/11/1057/2026/#xref_text.11)

[^27]: Ashkarkalaei, M., Ghiasi, R., Pakrashi, V., and Malekjafarian, A.: Feature selection for unsupervised defect detection of a wind turbine blade considering operational and environmental conditions, Mech. Syst. Signal Pr., 230, 112568, [https://doi.org/10.1016/j.ymssp.2025.112568](https://doi.org/10.1016/j.ymssp.2025.112568), 2025a. [a](https://wes.copernicus.org/articles/11/1057/2026/#xref_text.23), [b](https://wes.copernicus.org/articles/11/1057/2026/#xref_paren.42)

[^28]: Asian, S., Ertek, G., Haksoz, C., Pakter, S., and Ulun, S.: Wind Turbine Accidents: A Data Mining Study, IEEE Syst. J., 11, 1567–1578, [https://doi.org/10.1109/JSYST.2016.2565818](https://doi.org/10.1109/JSYST.2016.2565818), 2017. [a](https://wes.copernicus.org/articles/11/1057/2026/#xref_paren.2)

[^29]: Baquerizo, J., Tutivén, C., Puruncajas, B., Vidal, Y., and Sampietro, J.: Siamese Neural Networks for Damage Detection and Diagnosis of Jacket-Type Offshore Wind Turbine Platforms, Mathematics, 10, [https://doi.org/10.3390/math10071131](https://doi.org/10.3390/math10071131), 2022. [a](https://wes.copernicus.org/articles/11/1057/2026/#xref_text.10)

[^30]: Barreto, L. S., Machado, M. R., Santos, J. C., De Moura, B. B., and Khalij, L.: Damage indices evaluation for one-dimensional guided wave-based structural health monitoring, Lat. Am. J. Solids Stru., 18, 1–17, 2021. [a](https://wes.copernicus.org/articles/11/1057/2026/#xref_paren.42)

[^31]: Bishop, C. M.: Pattern Recognition and Machine Learning, Springer, 2nd edn., ISBN 978-1493938438, 2006. [a](https://wes.copernicus.org/articles/11/1057/2026/#xref_paren.41)

[^32]: Carmona-Troyo, J. A., Trujillo, L., Enríquez-Zárate, J., Hernandez, D. E., and Cárdenas-Florido, L. A.: Classification of Damage on Wind Turbine Blades Using Automatic Machine Learning and Pressure Coefficient, Expert Systems, 42, e70024, [https://doi.org/10.1111/exsy.70024](https://doi.org/10.1111/exsy.70024), 2025. [a](https://wes.copernicus.org/articles/11/1057/2026/#xref_paren.9)

[^33]: Chatzi, E., Abdallah, I., Hofsäß, M., Bischoff, O., Barber, S., and Marykovskiy, Y.: Aventa AV-7 ETH Zurich Research Wind Turbine SCADA and high frequency Structural Health Monitoring (SHM) data, Zenodo \[data set\], [https://doi.org/10.5281/zenodo.8229750](https://doi.org/10.5281/zenodo.8229750), 2023. [a](https://wes.copernicus.org/articles/11/1057/2026/#xref_text.39), [b](https://wes.copernicus.org/articles/11/1057/2026/#xref_paren.40), [c](https://wes.copernicus.org/articles/11/1057/2026/#xref_paren.50)

[^34]: Civera, M. and Surace, C.: Non-Destructive Techniques for the Condition and Structural Health Monitoring of Wind Turbines: A Literature Review of the Last 20 Years, Sensors, 22, [https://doi.org/10.3390/s22041627](https://doi.org/10.3390/s22041627), 2022. [a](https://wes.copernicus.org/articles/11/1057/2026/#xref_paren.6)

[^35]: Coelho, J. S., Machado, M. R., Dutkiewicz, M., and O. Teloli, R.: Data-driven machine learning for pattern recognition and detection of loosening torque in bolted joints, J. Braz. Soc. Mech. Sci., 46, [https://doi.org/10.1007/s40430-023-04628-6](https://doi.org/10.1007/s40430-023-04628-6), 2024. [a](https://wes.copernicus.org/articles/11/1057/2026/#xref_text.46)

[^36]: Coelho, J. S., Machado, M. R., and Dutkiewicz, M.: Integrating Virtual Sensor Data Augmentation Into Machine Learning for Damage Quantification of Bolted Structures Under Assembly Uncertainty, Structural Control and Health Monitoring, 2025, 8030 303, [https://doi.org/10.1155/stc/8030303](https://doi.org/10.1155/stc/8030303), 2025. [a](https://wes.copernicus.org/articles/11/1057/2026/#xref_text.46)

[^37]: Dervilis, N., Choi, M., Taylor, S., Barthorpe, R., Park, G., Farrar, C., and Worden, K.: On damage diagnosis for a wind turbine blade using pattern recognition, J. Sound Vib., 333, 1833–1850, [https://doi.org/10.1016/j.jsv.2013.11.015](https://doi.org/10.1016/j.jsv.2013.11.015), 2014b. [a](https://wes.copernicus.org/articles/11/1057/2026/#xref_text.17)

[^38]: de Sousa, A. A. S. R., da Silva Coelho, J., Machado, M. R., and Dutkiewicz, M.: Multiclass Supervised Machine Learning Algorithms Applied to Damage and Assessment Using Beam Dynamic Response, J. Vib. Eng. Technol., 11, 2709–2731, [https://doi.org/10.1007/s42417-023-01072-7](https://doi.org/10.1007/s42417-023-01072-7), 2023. [a](https://wes.copernicus.org/articles/11/1057/2026/#xref_text.45), [b](https://wes.copernicus.org/articles/11/1057/2026/#xref_text.47)

[^39]: Dutkiewicz, M. and Machado, M.: Measurements in Situ and Spectral Analysis of Wind Flow Effects on Overhead Transmission Lines, Sound & Vibration, 53, 161–175, [https://doi.org/10.32604/sv.2019.04803](https://doi.org/10.32604/sv.2019.04803), 2019a. [a](https://wes.copernicus.org/articles/11/1057/2026/#xref_paren.2)

[^40]: Dutkiewicz, M. and Machado, M.: Spectral Approach in Vibrations of Overhead Transmission Lines, IOP Conference Series: Materials Science and Engineering, 471, Session 4, [https://doi.org/10.1088/1757-899x/471/5/052029](https://doi.org/10.1088/1757-899x/471/5/052029), 2019b. [a](https://wes.copernicus.org/articles/11/1057/2026/#xref_paren.4)

[^41]: Dwivedi, D., Babu, K. V. S. M., Yemula, P. K., Chakraborty, P., and Pal, M.: Identification of surface defects on solar PV panels and wind turbine blades using attention based deep learning model, Eng. Appl. Artif. Intel., 131, 107836, [https://doi.org/10.1016/j.engappai.2023.107836](https://doi.org/10.1016/j.engappai.2023.107836), 2024. [a](https://wes.copernicus.org/articles/11/1057/2026/#xref_paren.8)

[^42]: Elforjani, M.: Diagnosis and prognosis of real world wind turbine gears, Renew. Energ., 147, 1676–1693, [https://doi.org/10.1016/j.renene.2019.09.109](https://doi.org/10.1016/j.renene.2019.09.109), 2020. [a](https://wes.copernicus.org/articles/11/1057/2026/#xref_paren.32)

[^43]: Farrar, C. R. and Worden, K.: Structural Health Monitoring: A Machine Learning Perspective, ISBN 9781119994336, [https://doi.org/10.1002/9781118443118](https://doi.org/10.1002/9781118443118), 2012. [a](https://wes.copernicus.org/articles/11/1057/2026/#xref_paren.7)

[^44]: Figueiredo, E., Park, G., Farrar, C. R., Worden, K., and Figueiras, J.: Machine learning algorithms to damage detection under operational and environmental variability, P. Soc. Photo-Opt. Ins., 7650, [https://doi.org/10.1117/12.849189](https://doi.org/10.1117/12.849189), 2010. [a](https://wes.copernicus.org/articles/11/1057/2026/#xref_paren.5)

[^45]: Flah, M., Nunez, I., Chaabene, W. B., and Nehdi, M.: Machine Learning Algorithms in Civil Structural Health Monitoring: A Systematic Review, Arch. Comput. Method. E., 28, 2621–2643, [https://doi.org/10.1007/s11831-020-09471-9](https://doi.org/10.1007/s11831-020-09471-9), 2020. [a](https://wes.copernicus.org/articles/11/1057/2026/#xref_paren.7)

[^46]: Gao, Q., Wu, X., Guo, J., Zhou, H., and Ruan, W.: Machine-Learning-Based Intelligent Mechanical Fault Detection and Diagnosis of Wind Turbines, Math. Probl. Eng., 2021, [https://doi.org/10.1155/2021/9915084](https://doi.org/10.1155/2021/9915084), 2021. [a](https://wes.copernicus.org/articles/11/1057/2026/#xref_text.34)

[^47]: Hoxha, E., Vidal, Y., and Pozo, F.: Damage Diagnosis for Offshore Wind Turbine Foundations Based on the Fractal Dimension, Appl. Sci., 10, [https://doi.org/10.3390/app10196972](https://doi.org/10.3390/app10196972), 2020. [a](https://wes.copernicus.org/articles/11/1057/2026/#xref_text.27)

[^48]: Joshuva, A. and Sugumaran, V.: A data driven approach for condition monitoring of wind turbine blade using vibration signals through best-first tree algorithm and functional trees algorithm: A comparative study, ISA Transactions, 67, 160–172, [https://doi.org/10.1016/j.isatra.2017.02.002](https://doi.org/10.1016/j.isatra.2017.02.002), 2017. [a](https://wes.copernicus.org/articles/11/1057/2026/#xref_paren.18)

[^49]: Joshuva, A., Vishnuvardhan, R., Deenadayalan, G., Sathishkumar, R., and Sivakumar, S.: Implementation of rule based classifiers for wind turbine blade fault diagnosis using vibration signals, International Journal of Recent Technology and Engineering, 8, 320–331, [https://doi.org/10.35940/ijrte.B1050.0982S1119](https://doi.org/10.35940/ijrte.B1050.0982S1119), 2019. [a](https://wes.copernicus.org/articles/11/1057/2026/#xref_paren.18)

[^50]: Knittel, D., Makich, H., and Nouari, M.: Milling diagnosis using artificial intelligence approaches, Software Impacts, 20, 809, [https://doi.org/10.1051/meca/2020053](https://doi.org/10.1051/meca/2020053), 2019. [a](https://wes.copernicus.org/articles/11/1057/2026/#xref_paren.42)

[^51]: Korolis, J. S., Bourdalos, D. M., and Sakellariou, J. S.: Machine Learning-Based Damage Diagnosis in Floating Wind Turbines Using Vibration Signals: A Lab-Scale Study Under Different Wind Speeds and Directions, Sensors, 25, [https://doi.org/10.3390/s25041170](https://doi.org/10.3390/s25041170), 2025. [a](https://wes.copernicus.org/articles/11/1057/2026/#xref_paren.24)

[^52]: Krishna, S. R., Sathish, J., Tarun, M., Rahul Mani Datta, T., and Vamsi, S. Raghu, a. S. S. J.: Machine Learning-Enabled Crack Diagnosis and Prognosis in Glass/Carbon Fiber Composite Structures, Iranian Journal of Science and Technology, Transactions of Mechanical Engineering, 49, 1511–1530, [https://doi.org/10.1007/s40997-025-00855-5](https://doi.org/10.1007/s40997-025-00855-5), 2025. [a](https://wes.copernicus.org/articles/11/1057/2026/#xref_text.13)

[^53]: Kuai, H., Civera, M., Coletta, G., Chiaia, B., and Surace, C.: Cointegration strategy for damage assessment of offshore platforms subject to wind and wave forces, Ocean Eng., 304, 117692, [https://doi.org/10.1016/j.oceaneng.2024.117692](https://doi.org/10.1016/j.oceaneng.2024.117692), 2024. [a](https://wes.copernicus.org/articles/11/1057/2026/#xref_paren.25)

[^54]: Kuo, J.-Y., You, S.-Y., Lin, H.-C., Hsu, C.-Y., and Lei, B.: Constructing Condition Monitoring Model of Wind Turbine Blades, Mathematics, 10, [https://doi.org/10.3390/math10060972](https://doi.org/10.3390/math10060972), 2022. [a](https://wes.copernicus.org/articles/11/1057/2026/#xref_paren.9)

[^55]: Lei, Z., Lin, H., Tang, X., Xiong, Y., and Wen, H.: Wind Turbine Blade Fault Detection Method Based on TROA-SVM, Sensors, 25, [https://doi.org/10.3390/s25030720](https://doi.org/10.3390/s25030720), 2025. [a](https://wes.copernicus.org/articles/11/1057/2026/#xref_paren.9)

[^56]: Leon-Medina, J. X., Anaya, M., Parés, N., Tibaduiza, D. A., and Pozo, F.: Structural Damage Classification in a Jacket-Type Wind-Turbine Foundation Using Principal Component Analysis and Extreme Gradient Boosting, Sensors, 21, [https://doi.org/10.3390/s21082748](https://doi.org/10.3390/s21082748), 2021. [a](https://wes.copernicus.org/articles/11/1057/2026/#xref_text.29)

[^57]: Li, W., Zhao, W., Wang, T., and Du, Y.: Surface Defect Detection and Evaluation Method of Large Wind Turbine Blades Based on an Improved Deeplabv3+ Deep Learning Model, Structural Durability & Health Monitoring, 18, 553, [https://doi.org/10.32604/sdhm.2024.050751](https://doi.org/10.32604/sdhm.2024.050751), 2024. [a](https://wes.copernicus.org/articles/11/1057/2026/#xref_paren.8)

[^58]: Li, W., Zhao, W., and Du, Y.: Large-scale wind turbine blade operational condition monitoring based on UAV and improved YOLOv5 deep learning model, Mech. Syst. Signal Pr., 226, 112386, [https://doi.org/10.1016/j.ymssp.2025.112386](https://doi.org/10.1016/j.ymssp.2025.112386), 2025. [a](https://wes.copernicus.org/articles/11/1057/2026/#xref_paren.8)

[^59]: Liu, H., Wang, Y., Zeng, T., Wang, H., Chan, S.-C., and Ran, L.: Wind turbine generator failure analysis and fault diagnosis: A review, IET Renewable Power Generation, 18, 3127–3148, [https://doi.org/10.1049/rpg2.13104](https://doi.org/10.1049/rpg2.13104), 2024. [a](https://wes.copernicus.org/articles/11/1057/2026/#xref_paren.4)

[^60]: Machado, M.: iMOSS-Lab/rp-wedowind-challenge-ASCE-EMI: v1, Version v1, Zenodo \[code\], [https://doi.org/10.5281/zenodo.18940555](https://doi.org/10.5281/zenodo.18940555), 2026. [a](https://wes.copernicus.org/articles/11/1057/2026/#xref_paren.49)

[^61]: Machado, M. and Dutkiewicz, M.: Wind turbine vibration management: An integrated analysis of existing solutions, products, and Open-source developments, Energy Reports, 11, 3756–3791, [https://doi.org/10.1016/j.egyr.2024.03.014](https://doi.org/10.1016/j.egyr.2024.03.014), 2024. [a](https://wes.copernicus.org/articles/11/1057/2026/#xref_paren.2)

[^62]: Meyer, A.: Vibration Fault Diagnosis in Wind Turbines Based on Automated Feature Learning, Energies, 15, [https://doi.org/10.3390/en15041514](https://doi.org/10.3390/en15041514), 2022. [a](https://wes.copernicus.org/articles/11/1057/2026/#xref_text.37)

[^63]: Milani, S., Leoni, J., Cacciola, S., Croce, A., and Tanelli, M.: A machine-learning-based approach for active monitoring of blade pitch misalignment in wind turbines, Wind Energ. Sci., 10, 497–510, [https://doi.org/10.5194/wes-10-497-2025](https://doi.org/10.5194/wes-10-497-2025), 2025. [a](https://wes.copernicus.org/articles/11/1057/2026/#xref_paren.31)

[^64]: Morozovska, K., Bragone, F., Svensson, A. X., Shukla, D. A., and Hellstenius, E.: Trade-offs of wind power production: A study on the environmental implications of raw materials mining in the life cycle of wind turbines, J. Clean. Prod., 460, 142578, [https://doi.org/10.1016/j.jclepro.2024.142578](https://doi.org/10.1016/j.jclepro.2024.142578), 2024. [a](https://wes.copernicus.org/articles/11/1057/2026/#xref_paren.5)

[^65]: Mousavi, Z., Varahram, S., Ettefagh, M. M., Sadeghi, M. H., Feng, W.-Q., and Bayat, M.: A digital twin-based framework for damage detection of a floating wind turbine structure under various loading conditions based on deep learning approach, Ocean Eng., 292, 116563, [https://doi.org/10.1016/j.oceaneng.2023.116563](https://doi.org/10.1016/j.oceaneng.2023.116563), 2024. [a](https://wes.copernicus.org/articles/11/1057/2026/#xref_paren.15)

[^66]: Movsessian, A., Cava, D. G., and Tcherniak, D.: Interpretable Machine Learning in Damage Detection Using Shapley Additive Explanations, ASCE-ASME J. Risk and Uncert. in Engrg. Sys. Part B Mech. Engrg., 8, 021101, [https://doi.org/10.1115/1.4053304](https://doi.org/10.1115/1.4053304), 2022. [a](https://wes.copernicus.org/articles/11/1057/2026/#xref_text.20)

[^67]: Nguyen, C. U., Huynh, T. C., and Kim, J. T.: Vibration-based damage detection in wind turbine towers using artificial neural networks, Structural Monitoring and Maintenance, 5, 507–519, [https://doi.org/10.12989/smm.2018.5.4.507](https://doi.org/10.12989/smm.2018.5.4.507), 2018. [a](https://wes.copernicus.org/articles/11/1057/2026/#xref_text.26)

[^68]: Praveen, H. M., Sabareesh, G., Inturi, V., and Jaikanth, A.: Component level signal segmentation method for multi-component fault detection in a wind turbine gearbox, Measurement, 195, 111180, [https://doi.org/10.1016/j.measurement.2022.111180](https://doi.org/10.1016/j.measurement.2022.111180), 2022. [a](https://wes.copernicus.org/articles/11/1057/2026/#xref_text.35)

[^69]: Regan, T., Beale, C., and Inalpolat, M.: Wind Turbine Blade Damage Detection Using Supervised Machine Learning Algorithms, J. Vib. Acoust., 139, 061010, [https://doi.org/10.1115/1.4036951](https://doi.org/10.1115/1.4036951), 2017. [a](https://wes.copernicus.org/articles/11/1057/2026/#xref_paren.9)

[^70]: Ren, L. and Yong, B.: Wind Turbines Fault Classification Treatment Method, Symmetry, 14, [https://doi.org/10.3390/sym14040688](https://doi.org/10.3390/sym14040688), 2022. [a](https://wes.copernicus.org/articles/11/1057/2026/#xref_text.30)

[^71]: Sharma, S. and Nava, V.: Condition monitoring of mooring systems for Floating Offshore Wind Turbines using Convolutional Neural Network framework coupled with Autoregressive coefficients, Ocean Eng., 302, 117650, [https://doi.org/10.1016/j.oceaneng.2024.117650](https://doi.org/10.1016/j.oceaneng.2024.117650), 2024. [a](https://wes.copernicus.org/articles/11/1057/2026/#xref_text.22)

[^72]: Smarsly, K., Dragos, K., Chowdhury, S., and Wiggenbrock, J.: Machine learning algorithms for structural health monitoring. 8th European Workshop on Structural Health Monitoring (EWSHM 2016), 5–8 July 2016, Bilbao, Spain, e-Journal of Nondestructive Testing, 21, [https://www.ndt.net/?id=19828](https://www.ndt.net/?id=19828), 2016. [a](https://wes.copernicus.org/articles/11/1057/2026/#xref_paren.7)

[^73]: Song, F., Han, Y., William Heath, A., and Hou, M.: Structural damage detection of floating offshore wind turbine blades based on Conv1d-GRU-MHA network, Eng. Fail. Anal., 166, 108896, [https://doi.org/10.1016/j.engfailanal.2024.108896](https://doi.org/10.1016/j.engfailanal.2024.108896), 2024. [a](https://wes.copernicus.org/articles/11/1057/2026/#xref_text.21)

[^74]: Tang, X., Huang, W., Li, X., and Ma, G.: Prediction of mooring tension of floating offshore wind turbines by CNN-LSTM-ATT and Chebyshev polynomials, Ocean Eng., 331, 121327, [https://doi.org/10.1016/j.oceaneng.2025.121327](https://doi.org/10.1016/j.oceaneng.2025.121327), 2025. [a](https://wes.copernicus.org/articles/11/1057/2026/#xref_paren.12)

[^75]: Thomas, D.: Unveiling Wind Turbine Failures Causes, Detection, and Prevention for Enhanced Reliability, Journal of Failure Analysis and Prevention, 24, 2051–2053, [https://doi.org/10.1007/s11668-024-02026-1](https://doi.org/10.1007/s11668-024-02026-1), 2024. [a](https://wes.copernicus.org/articles/11/1057/2026/#xref_paren.3)

[^76]: Tsiapoki, S., Häckell, M. W., Grießmann, T., and Rolfes, R.: Damage and ice detection on wind turbine rotor blades using a three-tier modular structural health monitoring framework, Struct. Health Monit., 17, 1289–1312, [https://doi.org/10.1177/1475921717732730](https://doi.org/10.1177/1475921717732730), 2018. [a](https://wes.copernicus.org/articles/11/1057/2026/#xref_text.19)

[^77]: Veers, P., Bottasso, C. L., Manuel, L., Naughton, J., Pao, L., Paquette, J., Robertson, A., Robinson, M., Ananthan, S., Barlas, T., Bianchini, A., Bredmose, H., Horcas, S. G., Keller, J., Madsen, H. A., Manwell, J., Moriarty, P., Nolet, S., and Rinker, J.: Grand challenges in the design, manufacture, and operation of future wind turbine systems, Wind Energ. Sci., 8, 1071–1131, [https://doi.org/10.5194/wes-8-1071-2023](https://doi.org/10.5194/wes-8-1071-2023), 2023.  [a](https://wes.copernicus.org/articles/11/1057/2026/#xref_paren.1)

[^78]: Vidal, Y., Aquino, G., Pozo, F., and Gutiérrez-Arias, J. E. M.: Structural Health Monitoring for Jacket-Type Offshore Wind Turbines: Experimental Proof of Concept, Sensors, 20, [https://doi.org/10.3390/s20071835](https://doi.org/10.3390/s20071835), 2020. [a](https://wes.copernicus.org/articles/11/1057/2026/#xref_text.28)

[^79]: Vives, J.: Vibration analysis for fault detection in wind turbines using machine learning techniques, Adv. Intell. Soft. Comp., 2, 1–12, [https://doi.org/10.1007/s43674-021-00029-1](https://doi.org/10.1007/s43674-021-00029-1), 2022. [a](https://wes.copernicus.org/articles/11/1057/2026/#xref_text.36)

[^80]: Vives, J., Roses Albert, E., Quiles, E., Palací, J., and Fuster, T.: Vibration Analysis for Fault Detection of Wind Turbines by Combining Machine-Learning Techniques and 3D Scanning Laser, Genet. Res., 2022, [https://doi.org/10.1155/2022/2093086](https://doi.org/10.1155/2022/2093086), 2022. [a](https://wes.copernicus.org/articles/11/1057/2026/#xref_text.36)

[^81]: Wang, S., Vidal, Y., and Pozo, F.: Recent advances in wind turbine condition monitoring using SCADA data: A state-of-the-art review, Reliab. Eng. Syst. Safe., 267, 111838, [https://doi.org/10.1016/j.ress.2025.111838](https://doi.org/10.1016/j.ress.2025.111838), 2026. [a](https://wes.copernicus.org/articles/11/1057/2026/#xref_text.48)

[^82]: Zarrin, P. S., Martin, C., Langendoerfer, P., Wenger, C., and Diaz, M.: Vibration Analysis of a Wind Turbine Gearbox for Off-cloud Health Monitoring through Neuromorphic-computing, IECON Proceedings (Industrial Electronics Conference), 2021-October, [https://doi.org/10.1109/IECON48115.2021.9589879](https://doi.org/10.1109/IECON48115.2021.9589879), 2021. [a](https://wes.copernicus.org/articles/11/1057/2026/#xref_text.33)

[^83]: Zhang, S., Wang, T., Worden, K., Sun, L., and Cross, E. J.: Canonical-correlation-based fast feature selection for structural health monitoring, Mech. Syst. Signal Pr., 223, 111895, [https://doi.org/10.1016/j.ymssp.2024.111895](https://doi.org/10.1016/j.ymssp.2024.111895), 2025. [a](https://wes.copernicus.org/articles/11/1057/2026/#xref_text.43), [b](https://wes.copernicus.org/articles/11/1057/2026/#xref_text.44)

[^84]: Zhao, W., Li, W., and Du, Y.: Wind turbine blade rotational condition monitoring based on RBs-YOLO deep learning model, Mech. Syst. Signal Pr., 230, 112641, [https://doi.org/10.1016/j.ymssp.2025.112641](https://doi.org/10.1016/j.ymssp.2025.112641), 2025. [a](https://wes.copernicus.org/articles/11/1057/2026/#xref_paren.8)