# Conclusion

This project demonstrated the potential and limitations of deep learning approaches for diabetic retinopathy detection, using a limited dataset of about 3600 images. We trained and evaluated three models:

- **Baseline CNN:** Simple architecture that achieved solid performance but struggled with more severe cases (0.7074 QWK)

- **ResNet-50:** Much deeper model that learned more useful features, but also struggled with severe cases (0.8136 QWK)

- **EfficientNet-B4:** Efficient, accurate model that performed consistently, handling underrepresented cases best (0.8339 QWK)

While EfficientNet-B4 achieved superior quantitative performance, GradCAM analysis revealed some interpretability issues with all models. While some cases showed attention to relevant hemorrhages and abnormal blood vessels, the focus on edge artifacts and eye borders indicates a need for these models to understand pathological features better. Additionally, the universal struggle with severe cases across all models highlights a critical gap between algorithmic performance and clinical needs. This emphasizes how positive initial results, like a high QWK, can be misleading if they do not fully encapsulate what is necessary for the problem, such as detecting severe cases.

The results underscore that model selection for medical AI requires balancing quantitative metrics with interpretability and clinical appropriateness. Future work must prioritize addressing class imbalance, improving severe case detection, and developing more clinically interpretable architectures. You are encouraged to experiment with different preprocessing techniques, add more data and apply synthetic data augmentation. Additionally, many improvements can be made by exploring different models and sampling methods. When experimenting with different models, use Grad-CAM to understand how they focus on different parts of the retina. Hopefully, this gives you a good initial idea about how deep learning models can be used for medical imaging tasks and the challenges they face.