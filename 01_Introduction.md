
# Introduction

---

## What is Diabetic Retinopathy?

Diabetic Retinopathy is an eye condition in people with diabetes and is the leading cause of blindness among working aged adults. The condition is caused by high blood sugar levels, which damage the blood vessels in the retina. Our goal is to build a model that can accurately diagnose the level of severity of diabetic retinopathy through retina images.

---

## Why is this an important problem?
- **Silent progression**: DR often shows no symptoms in its early stages.
- **Preventable vision loss**: With timely treatment, many of these vision loss cases can be prevented.
- **Growing medical burden**: Deep learning models address the increasing need for scalable and accessible screening tools as diabetes becomes more prevalent.

---

## Machine Learning Approach

Machine learning, especially deep learning with convolutional neural networks (CNNs), has shown great promise in analyzing medical images. In this book, we cover:

- The preprocessing of retinal fundus images
- Training deep learning models for DR classification
- Evaluating model performance and addressing class imbalance
- Comparing model outputs with clinical grading standards

By the end, you'll understand how automated DR detection systems can support clinicians, reduce screening costs, and help deliver faster diagnoses—especially in underserved regions.

---

## Dataset

We will use a dataset from Aravind Eye Hospital, which includes retinal fundus images and corresponding DR severity levels labeled by clinicians. The severity ratings range from 0-4, with 0 representing no DR and 4 representing proliferative DR.
