# ML_Challenge_Terafac
Multi-Stage Image Classification on CIFAR-10

Author: Yash

📌 Project Summary

This project presents a structured, multi-stage approach to image classification on the CIFAR-10 dataset. Rather than applying all techniques simultaneously, the model is progressively enhanced across multiple levels. This design allows a clear understanding of how each architectural or training modification influences performance.

Starting from a strong transfer-learning baseline, the pipeline evolves through data augmentation, optimization strategies, attention mechanisms, and finally ensemble learning. The focus is not only on improving accuracy, but also on maintaining reproducibility, interpretability, and experimental clarity at every stage.

🎯 Problem Definition

The goal of this project is to build a stable and high-performing image classification system for CIFAR-10. By incrementally refining the model across defined stages, the project demonstrates how thoughtful architectural choices and training strategies contribute to measurable performance gains while effectively controlling overfitting.

📊 Dataset Description

Dataset: CIFAR-10

Total Images: 60,000

Image Type: RGB

Resolution: 32 × 32

Number of Classes: 10

Classes:
airplane, automobile, bird, cat, deer, dog, frog, horse, ship, truck

🔀 Dataset Splitting Strategy
Original Dataset

Training set: 50,000 images

Test set: 10,000 images

Split Used in This Project

Training: 40,000 images

Validation: 10,000 images

Test: 10,000 images

A dedicated validation set was created from the training data to monitor model performance and reduce the risk of overfitting.

🧪 Methodology and Experimental Results
Level 1 — Transfer Learning Baseline

Model: ResNet-50

Strategy: Transfer learning using pretrained weights

Test Accuracy: 90.63%

This stage establishes a strong baseline by leveraging pretrained convolutional features. Even with minimal task-specific tuning, the model achieves robust performance, highlighting the effectiveness of transfer learning for small-resolution image datasets such as CIFAR-10.

Level 2 — Data Augmentation and Training Optimization

Enhancements Applied:

Random cropping

Horizontal flipping

Learning-rate scheduling

Improved regularization techniques

Model: ResNet-50

Test Accuracy: 93.08%

Data augmentation and optimization significantly improve generalization. These techniques reduce overfitting and encourage the network to learn more invariant and robust feature representations.

Level 3 — Channel-Wise Attention Mechanism

Model: SE-ResNet-50

Technique: Squeeze-and-Excitation (SE) blocks

Test Accuracy: 94.35%

Channel-wise attention dynamically recalibrates feature responses by emphasizing informative channels and suppressing less relevant ones. This results in consistent performance improvements across most classes and represents the strongest single-model configuration.

🧠 Key Takeaways

Transfer learning provides a powerful foundation even for small images.

Data augmentation and learning-rate scheduling yield substantial gains with minimal architectural changes.

Attention mechanisms further refine feature learning and enhance classification accuracy.

A level-wise experimental framework makes performance improvements interpretable and reproducible.

🚀 Final Performance — Ensemble Learning

Final Test Accuracy: 94.72%

The final model utilizes an ensemble of multiple high-performing architectures. By combining predictions from diverse models, the ensemble reduces individual model biases and variance, leading to a more stable and reliable classification system.

This approach is particularly effective for visually similar CIFAR-10 classes, where single models often struggle to draw clear decision boundaries.

📈 Performance Summary
Stage	Model	Test Accuracy
Level 1	ResNet-50 (Transfer Learning)	90.63%
Level 2	ResNet-50 + Augmentation & Optimization	93.08%
Level 3	SE-ResNet-50 (Channel Attention)	94.35%
Final Level	Ensemble Model	94.72%

Each stage introduces targeted improvements, resulting in steady and interpretable performance gains rather than abrupt changes.

🔍 Analysis

Ensemble learning reduces over-reliance on individual model feature biases.

Predictions become more consistent across runs, improving overall stability.

Common misclassifications—such as cat vs dog and automobile vs truck—are significantly reduced.

Averaging predictions smooths decision boundaries, leading to improved generalization on unseen data.

📝 Observations

Incremental architectural improvements consistently outperform one-shot complex designs.

Attention mechanisms provide strong gains, while ensemble learning offers the final refinement.

Performance improvements diminish at higher accuracy levels, indicating proximity to the dataset’s practical performance ceiling.

The ensemble model achieves superior robustness without requiring additional labeled data.
