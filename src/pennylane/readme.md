# Quantum Classifiers for Medical Imaging



This repository contains implementations of quantum classifiers applied to medical imaging, including various quantum neural networks, hybrid architectures, and support vector machines (QSVM). The project explores numerous configurations, including different feature extraction methods such as PCA and DCT2, and fusion across multiple imaging planes.



## Introduction: Why Pennylane?
![Pennylane Logo](logoPenylane.svg)

Using Pennylane Framework

This repository leverages the **Pennylane framework**, a cutting-edge software platform for quantum machine learning, quantum computing, and quantum simulation. Pennylane provides a user-friendly and powerful interface to develop hybrid quantum-classical models, seamlessly integrating quantum circuits into machine learning pipelines. 

### Why Choose Pennylane?
1. **Hybrid Quantum-Classical Approach**: Pennylane specializes in hybrid workflows, enabling the integration of quantum computation with classical machine learning libraries like TensorFlow, PyTorch, and scikit-learn.
2. **Device Agnosticism**: It supports a wide range of quantum hardware (e.g., IBM Q, Rigetti, and Xanadu’s own photonic quantum computers) and simulators, making it versatile and adaptable.
3. **Automatic Differentiation**: The framework allows for automatic differentiation of quantum circuits, facilitating the optimization of quantum models in a manner similar to classical neural networks.
4. **Ease of Use**: Pennylane’s Pythonic interface is intuitive and integrates seamlessly into existing ML and data science workflows.
5. **Extensive Community and Documentation**: Its rich documentation and active community make it an ideal choice for both research and development.


By using Pennylane, this project benefits from state-of-the-art quantum software tailored to the needs of quantum machine learning research and experimentation.

---

## Notebooks and Results

### Quantum Neural Networks and Hybrid Architectures
The following notebooks explore quantum neural network architectures and hybrid quantum-classical approaches:

- [Quantum Pennylane Neural Network (Coronal Plane)](https://colab.research.google.com/drive/1fPocsN_QRsmKPKKEtMd97QIhdD7uc2i0?usp=sharing)
- [Quantum Pennylane Hybrid Architectures (Coronal Plane)](https://colab.research.google.com/drive/1jAzbUpFsK9FcaeJEW4MEePDWh1mmsTDX?usp=sharing)


### Quantum Support Vector Machines (QSVM)
Significant performance improvements were observed using QSVM models. Below are links to the successful implementations:

#### Individual Imaging Planes
- [Coronal Plane + PCA](https://colab.research.google.com/drive/1WY6ybYvei3Oq74jCEMSglxYhEf_H_HjU?usp=sharing)
- [Coronal Plane + DCT2](https://colab.research.google.com/drive/1W1dcBg95BaORs5n2kgg1GYdEXh3Sbqqt?usp=sharing)
- [Sagittal Plane + PCA](https://colab.research.google.com/drive/1qFeVQsS7soQZl4cbI7yPZtqJ74W1Bjos?usp=sharing)
- [Sagittal Plane + DCT2](https://colab.research.google.com/drive/10SOTcLBeRt1mW3NaQAkI51oGLDtVvNfP?usp=sharing)
- [Axial Plane + PCA](https://colab.research.google.com/drive/1zpzdtHz_vkmfHbwUHjpvzlkrv2YJfuKd?usp=sharing)
- [Axial Plane + DCT2](https://colab.research.google.com/drive/153uIwN7wyKmcSbwOJ4-pHYgLvUACwMh4?usp=sharing)

#### Fusion and Ensemble Approaches
- [Coronal + Sagittal + Axial with PCA](https://colab.research.google.com/drive/1Ojtp-5y9MzPF3LYVSGaeFGPqNPhra_b8?usp=sharing)
- [Coronal + Sagittal + Axial with DCT2](https://colab.research.google.com/drive/1-dQ4hVf4_nWec9xgUt4D9sgKJHk-nlRt?usp=sharing)
- [Coronal + Sagittal + Axial with PCA and Ensemble Methods](https://colab.research.google.com/drive/1jd_MJdVlFbqRSigEtp99dR8W9b_OuDd3?usp=sharing)

---

## Code Highlights

### Quantum Support Vector Machine (QSVM) Implementation

The QSVM is implemented using Pennylane and scikit-learn, enabling kernel-based quantum machine learning. Below is a snippet of the main QSVM framework:

```python
import pennylane as qml
import numpy as np
from sklearn.svm import SVC
import timeit

nqubits = 5
dev1 = qml.device("lightning.qubit", wires=nqubits)

@qml.qnode(dev1)
def kernel_circ1(a, b):
    qml.AmplitudeEmbedding(a, wires=range(nqubits), pad_with=0, normalize=True)
    qml.adjoint(qml.AmplitudeEmbedding(b, wires=range(nqubits), pad_with=0, normalize=True))
    return qml.probs(wires=range(nqubits))

def qkernel1(A, B):
    return np.array([[kernel_circ1(a, b)[0] for b in B] for a in A])

# Example: Training a QSVM model
print("Training QSVM model")
start_time = timeit.default_timer()
model1 = SVC(kernel=qkernel1).fit(X_train1, Y_train)
end_time = timeit.default_timer()
print(f"The QSVM executed in {end_time - start_time:.2f} seconds")

# Predictions
Y_test_pred1 = model1.predict(X_val1)
print("Test predictions complete")
```

---

## Key Features
1. **Quantum Neural Networks**: Exploration of hybrid quantum-classical architectures.
2. **QSVM**: Demonstrates notable performance for classification tasks using quantum kernels.
3. **Feature Extraction**: Utilizes PCA and DCT2 for dimensionality reduction.
4. **Fusion and Ensembles**: Combines multiple imaging planes for enhanced performance.

---


---
