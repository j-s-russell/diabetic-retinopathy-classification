# Next Steps

**Extensions:** 
- Experiment with other methods to handle class imbalance, such as weighted sampling or oversampling/undersampling.
- Data augmentation would also be greatly beneficial for models to better understand underrepresented classes.
- With a larger dataset, it would be more practical to train models from scratch instead of relying on ImageNet transfer learning.
- As for modeling, try ensembling methods, such as a weighted average of predictions or model stacking.

**Additional Metrics:**
- [Youden's Index](https://pmc.ncbi.nlm.nih.gov/articles/PMC2749250/): Balances sensitivity (true positive rate) and specificity (true negative rate). This can be a more effective classification threshold as it places more emphasis on true negatives and is also more interpretable to clinicians.
- [Calibration](https://scikit-learn.org/stable/modules/calibration.html): Improves the reliability and interpretability by adjusting the model's predicted probabilities to better reflect true likelihoods.

**Production Considerations:** 
- Implement confidence thresholding to flag uncertain predictions for human review and develop comprehensive testing protocols including edge cases, image quality variations, and demographic bias assessment. 
- Since retinal imaging equipment and patient populations may differ from training data, establish robust model monitoring to account to identify changes in underlying image patterns.

**Expanded Project Ideas:** 
- Try expanding to multi-modal diagnosis by incorporating patient metadata (age, diabetes duration, etc.) alongside fundus images for improved prediction accuracy. 
- Develop progression prediction models using longitudinal patient data to forecast DR advancement over time.