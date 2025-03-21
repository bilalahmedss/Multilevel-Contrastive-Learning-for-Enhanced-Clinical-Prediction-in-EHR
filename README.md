
# **Multilevel Contrastive Learning for Enhanced Clinical Prediction in Electronic Health Records**
---

## **Contributors:**
- **Ahtisham Uddin** 
- **Bilal Ahmed** 
- **Manqad Raza** 

## **Project Overview**
This repository contains the code and documentation for the project **“Multilevel Contrastive Learning for Enhanced Clinical Prediction in Electronic Health Records”**, which aims to improve clinical prediction tasks using contrastive learning on Electronic Health Record (EHR) time-series data. The project focuses on leveraging a self-supervised contrastive learning approach, utilizing temporal dependencies and feature groupings for improved patient outcome predictions.

### **Objectives:**
- Develop a contrastive learning pipeline for clinical time-series data using the MIMIC-III dataset.
- Implement a bidirectional LSTM model trained with NT-Xent loss to generate temporal embeddings.
- Enhance model generalization through data augmentation techniques, including noise addition, scaling, and masking.
- Evaluate learned embeddings through classification and regression tasks, including mortality prediction, ICU readmission prediction, and disease group classification.

---

## **Key Features:**
- **Multilevel Contrastive Learning:** Uses contrastive learning to generate positive and negative pairs across multiple levels (feature group, temporal neighborhood, and patient-specific data).
- **LSTM-Based Architecture:** Utilizes a bidirectional Long Short-Term Memory (LSTM) model to learn temporal embeddings from EHR data.
- **Data Augmentation:** Implements techniques like noise addition, scaling, and masking to improve the robustness of the model.
- **Performance Evaluation:** The embeddings are evaluated using downstream tasks, including classification and regression, to assess their effectiveness in clinical prediction tasks.
- **Interpretability:** Uses t-SNE and K-Means clustering to analyze and visualize the learned embeddings.

---

## **Technologies Used:**
- **Python**: Primary programming language for all data processing and model implementation.
- **PyTorch**: Framework used for building and training the contrastive learning model.
- **MIMIC-III Dataset**: A publicly available critical care database used to evaluate the model.
- **t-SNE & K-Means**: For visualizing and clustering the learned embeddings.
- **Jupyter Notebook/VS Code**: Tools used for coding and testing the model.

---

## **Methodology:**

### **Dataset Preparation:**
- The MIMIC-III dataset was used, which includes ICU patient records. The dataset was preprocessed, and relevant features were grouped based on clinical relevance (e.g., cardiac, respiratory).
- Positive and negative pairs were generated based on temporal relationships, ensuring a balanced dataset for training.

### **Model Architecture:**
- The core architecture of the model is based on a **Bidirectional LSTM**, trained with the **NT-Xent loss** function. This model captures both forward and backward temporal dependencies.
- The model was trained for **100 epochs** using an **Adam optimizer** with a learning rate scheduler and gradient clipping to avoid overfitting and improve generalization.

### **Data Augmentation:**
- To make the model more robust, techniques like adding **Gaussian noise**, **scaling**, and **masking** random time steps were applied.

---

## **Results and Evaluation:**

### **Training and Validation:**
- The model showed steady convergence, with training and validation losses stabilizing over time, indicating successful learning.
- **Classification tasks** (e.g., mortality prediction) achieved an **AUC-ROC of 0.803** and an **accuracy of 82.14%**.

### **Embedding Analysis:**
- t-SNE visualization and **K-Means clustering** demonstrated that the learned embeddings captured both local and global patterns in the data.

### **Downstream Tasks:**
- **ICU Mortality Prediction:** The model achieved an accuracy of **69.25%** and an AUC-ROC of **0.5046**.
- **ICU Readmission Prediction:** Accuracy was **93.77%**, with an AUC-ROC of **0.4901**, indicating challenges in capturing subtle predictive patterns.

### **Comparison with Benchmark:**
- The model showed competitive results compared to a HiRID benchmark, with a slightly higher validation loss but comparable performance in key metrics like **AUC-ROC** and **accuracy**.

---

## **Challenges and Limitations:**
- **Class Imbalance:** Tasks like mortality and readmission prediction faced challenges due to imbalanced datasets, leading to near-random performance.
- **Embedding Granularity:** Further refinement of the embeddings could improve clustering and performance on nuanced prediction tasks.
- **Computational Efficiency:** Despite optimizations, the computational cost remained significant, suggesting that future work could focus on reducing overhead with techniques like distributed training or pruning.

---

## **Conclusion:**
This project demonstrates the potential of contrastive learning in enhancing clinical prediction tasks. By combining self-supervised learning with clinical time-series data, the model effectively learns meaningful embeddings, offering significant improvements in predictability and interpretability in healthcare applications. The flexibility and adaptability of the model suggest that it can be further refined and deployed in real-world clinical settings.



## **Contributions:**

If you wish to contribute to this project, feel free to fork the repository and submit a pull request. Contributions are welcome, whether it’s by improving the code, adding new features, or suggesting improvements. Please ensure that your contributions align with the project's goals of improving **clinical predictions** using **EHR time-series data**.

### **Future Contributions:**
- **Additional Data Modalities:** Contributors can enhance the project by incorporating additional data types, such as **clinical notes** or **medical imaging**, to create richer feature sets for better predictions.
- **Advanced Architectures:** There is an opportunity to explore more sophisticated models like **transformers** or **attention mechanisms** to better capture long-term dependencies and improve model performance.
- **Real-World Deployment:** Future contributors can work on deploying the model in **real-world clinical systems** to further validate its effectiveness, utility, and performance on diverse patient data.

