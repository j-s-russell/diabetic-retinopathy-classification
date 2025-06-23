# Limitations

---

## What did these models struggle with?

Despite EfficientNet-B3 achieving the best quantitative performance, several critical limitations emerged that challenge clinical viability. GradCAM analysis revealed concerning interpretability issues, with EfficientNet showing diffuse, blob-like attention patterns that poorly correspond to visible pathological features. All models demonstrated an inverse performance-severity relationship, achieving excellent results on healthy cases (96.5% F1) but failing catastrophically on the most clinically urgent Proliferative DR cases (29.0% average F1), missing the majority of sight-threatening conditions that require immediate intervention.
Class imbalance severely impacted performance, with rare severe classes receiving insufficient training examples, while the models showed concerning edge artifacts in GradCAM visualizations, indicating potential dependence on image preprocessing artifacts rather than pathological features. The transfer learning approach, while computationally efficient, may have introduced biases from natural image pretraining that don't translate appropriately to medical imaging tasks.

---

## How can we improve?

Data augmentation could be very beneficial. Given the class imbalance, datasets with more severe cases would help our models significantly. Combining datasets from different institutions and imaging equipment would also improve model robustness and generalization. Ensemble methods could be explored to leverage the complementary strengths observed across architectures - combining ResNet's superior spatial localization capabilities with EfficientNet's overall performance while mitigating individual model failure through voting or confidence-weighted predictions.
Training from scratch on medical data rather than relying on ImageNet transfer learning could eliminate the biases introduced by natural image pretraining, allowing models to learn features specifically relevant to retinal pathology. This approach, combined with larger medical datasets, would enable models to develop more clinically appropriate attention patterns and reduce reliance on image artifacts, ultimately producing more trustworthy and interpretable AI systems for diabetic retinopathy screening.