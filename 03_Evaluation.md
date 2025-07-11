# Evaluation Methods

---

## Precision, Recall, and F1-Score

Precision, Recall, and F1-score are core metrics used to evaluate classification performance, especially when class distributions are imbalanced. They are typically computed per class and averaged to summarize performance in multiclass problems like ours ([scikit-learn docs](https://scikit-learn.org/stable/modules/generated/sklearn.metrics.precision_recall_fscore_support.html)).


For the evaluation of a given class, we define 4 types of predictions:

```{admonition} Note
:class: info
- **True Positive (TP):** The model correctly predicts an image as belonging to the given class.
- **False Positive (FP):** The model incorrectly predicts an image as the given class when it actually belongs to another class.
- **False Negative (FN):** The model fails to predict an image as the given class when it actually belongs to that class.
- **True Negative (TN):** The model correctly predicts that an image does not belong to the given class when it truly does not belong to the given class.
```

Given these definitions, we define precision, recall, and F1-score with the formulas below:

````{grid} 1 2 2 3
:gutter: 3

```{grid-item-card} Precision
:class-header: bg-primary text-white
- $\frac{TP}{TP+FP}$
- Measures how many predicted positives are correct.
```

```{grid-item-card} Recall
:class-header: bg-secondary text-white
- $\frac{TP}{TP+FN}$
- Measures how many actual positives were correctly identified.
```

```{grid-item-card} F1-Score
:class-header: bg-success text-white
- $2 \times (\frac{Precision \times Recall}{Precision + Recall})$
- Balances precision and recall, capturing the trade-off between missing cases and making false alarms
```
````

#### Benefits
- These metrics give a clear picture of how well the model handles imbalanced DR severity cases (accuracy alone might hide poor performance on rarer but critical cases)
- They help display the trade-offs between overdiagnosis and missed severe cases

#### Limitations
- F1-score can hide class imbalance: A high F1 may come from doing well on frequent classes only.
- Precision and recall must be considered together: One can be high while the other is low, so they should not be interpreted in isolation.

---

## ROC (Receiver Operating Characteristic)
The [ROC Curve](https://scikit-learn.org/stable/auto_examples/model_selection/plot_roc.html) visualizes the trade-off between the true positive rate (recall) and the false positive rate at various classification thresholds. It is widely used to evaluate the discriminative ability of binary classifiers and can be extended to multiclass problems via a one-vs-rest approach (like our case).

#### Why Use ROC?
- ROC curves help you understand how well your model separates classes across different decision thresholds, which is useful for tuning sensitivity and specificity in medical diagnosis tasks.

#### Interpretation
- Area under the curve (AUC) ranges from 0.5 (random guessing) to 1.0 (perfect classification).
- Higher AUC means better model performance in distinguishing positive from negative cases.

#### Limitations
- ROC can be overly optimistic with imbalanced data, since it considers false positive rate, which may be low if negatives dominate.
- For multiclass tasks, multiple one-vs-rest ROC curves are needed, which can complicate interpretation.

---

## PRC (Precision-Recall Curve)
- The [Precision-Recall Curve](https://scikit-learn.org/stable/auto_examples/model_selection/plot_precision_recall.html) plots the trade-off between precision and recall across different classification thresholds. It is especially valuable for evaluating models on imbalanced datasets, like diabetic retinopathy severity classification, where positive cases are less frequent.

#### Why Use PRC?
- PRC provides a clearer picture of model performance on the minority (positive) class by focusing on how many positive predictions are correct (precision) and how many actual positives are identified (recall).

#### Interpretation
- The area under the PR curve (AUC-PR) ranges from the baseline (proportion of positives) to 1.0 (perfect precision and recall).
- Higher AUC-PR indicates better performance at identifying positive cases with fewer false alarms.

#### Limitations
- Like ROC, PR curves are typically computed in a one-vs-rest manner for multiclass problems, which can complicate overall interpretation.
- PRC focuses on positive class performance and may not fully reflect performance on all classes in multiclass settings.

---

## Quadratic Weighted Kappa (QWK)

**Quadratic Weighted Kappa (QWK)** is a metric for evaluating agreement between two sets of ratings — typically the **true labels** and **predicted labels** in an ordinal classification task. It adjusts for agreement occurring by chance and penalizes larger disagreements more heavily ([scikit-learn docs](https://scikit-learn.org/stable/modules/generated/sklearn.metrics.cohen_kappa_score.html)).

#### Why Use QWK?
Unlike accuracy or unweighted kappa, QWK considers **how far off** predictions are. For example, predicting "3" instead of "4" is better than predicting "1" instead of "4". For our problem, this is important as predictions that classify high-severity cases as "0" or "1" could ignore early treatment while vision loss is still preventable.

---

#### Formula

$$
\kappa = 1 - \frac{\sum_{i,j} w_{i,j} \cdot O_{i,j}}{\sum_{i,j} w_{i,j} \cdot E_{i,j}}
$$

Where:
- $O$ is the **observed matrix** (confusion matrix of predictions vs. true labels).
- $E$ is the **expected matrix** (expected agreement by chance).
- $w_{i,j} = \frac{(i - j)^2}{(N - 1)^2}$ is the **quadratic weight** for the difference between classes $i$ and $j$.
- $N$ is the number of classes.

---

#### Interpretation
- $ \kappa = 1 $: perfect agreement
- $ \kappa = 0 $: agreement is no better than random
- $ \kappa < 0 $: worse than chance

---

#### Limitations
- **Target Label Imbalance**: Although QWK accounts for chance agreement, imbalanced classes can lead to biased predictions.
- **Lack of Interpretability**: Simpler metrics like precision and recall make prediction quality easier to understand.

---
