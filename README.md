# QTMLforBiomedicalImages_ComparativeStudy
Quantum Machine Learning in Biomedical Applications: A Comparative Study. 

---

# Quantum Machine Learning in Biomedical Applications: A Comparative Study

## Authors
- Xavi F. Aragones¹²
- Miguel A. González Ballester¹³⁴

### Affiliations
1. BCN Medtech, Dept. of Engineering, Universitat Pompeu Fabra, Barcelona, Spain
2. Parc Tecnològic TecnoCampus Mataró-Maresme - UPF, Spain
3. Quantic, Barcelona Supercomputing Center, Barcelona, Spain
4. ICREA, Barcelona, Spain

## Introduction
Quantum Machine Learning (QML) has emerged as a promising paradigm, offering significant potential for applications in biomedicine. The accessibility and democratization of various quantum computing simulation tools have facilitated a smoother transition from classical machine learning to QML. This paper focuses on analyzing a classical image classification problem, with a particular emphasis on the use of real medical images, such as those used for recognizing malignant tumors in CT scans [1]. The primary contribution of this work is a comprehensive comparison of different QML software frameworks and the investigation of classical data encoding within fully quantum and hybrid quantum frameworks.

## Methods
This study explores two prominent approaches commonly employed in quantum image processing: quantum image encoding techniques and classical image data encoding for quantum processing. The first approach utilizes quantum image encoding techniques, such as Flexible Representation of Quantum Images (FRQI) and Novel Enhanced Quantum Representation (NEQR), to leverage their inherent advantages.

The second approach treats images as classical data, deploying various encoding strategies, including:
- Amplitude encoding
- Angle encoding
- ZZ feature map

To address the limitations posed by quantum resource constraints, dimensionality reduction techniques were integrated:
- Principal Component Analysis (PCA)
- 2D Discrete Cosine Transform (DCT2)

Variational Quantum Classifiers (VQCs) and Quantum Support Vector Machines (QSVMs) were employed as the primary quantum classification techniques [2, 3].

## Results
Among the implemented quantum classification techniques, the Quantum Support Vector Machine demonstrated superior performance compared to other methods, including Quantum Neural Networks (QNNs) and hybrid architectures. This indicates the potential of QSVM in achieving higher accuracy and efficiency in the classification of medical images, highlighting their applicability in real-world biomedical scenarios.

### Performance Results

| Embedding  | Coronal Avg. Acc. | Sagittal Avg. Acc. | Axial Avg. Acc. |
|------------|-------------------|-------------------|-----------------|
| Amplitude  | 0.813            | 0.768            | 0.757          |
| Angle      | 0.841            | 0.766            | 0.787          |
| ZZFeatMap  | 0.804            | 0.793            | 0.822          |


![CT planes with examples of benign and malignant lung nodules](figures/lungNoduleCT.jpg)


## Acknowledgements
This work is part of Maria de Maeztu Units of Excellence Programme CEX2021-001195-M, funded by MICIU/AEI /10.13039/501100011033

## References
[1] Pedrosa, et al. (2019)  
[2] Huang, et al. (2020)  
[3] Schuld, et al. (2021)
