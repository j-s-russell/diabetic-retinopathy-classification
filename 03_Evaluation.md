# Evaluation Methods

## Quadratic Weighted Kappa (QWK)

**Quadratic Weighted Kappa (QWK)** is a metric for evaluating agreement between two sets of ratings — typically the **true labels** and **predicted labels** in an ordinal classification task. It adjusts for agreement occurring by chance and penalizes larger disagreements more heavily.

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
- **Lack of Interpretability**: Simpler metrics like balanced accuracy make prediction quality easier to understand.
