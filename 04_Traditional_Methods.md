# Traditional Methods (Basic CNN)

---

## Baseline Model

Our first model will be a traditional CNN with a straightforward architecture consisting of multiple convolutional layers followed by pooling operations, batch normalization, and fully connected layers for classification. This approach uses sequential convolutional blocks to progressively extract hierarchical features from retinal images, starting with low-level edges and textures in early layers and building up to complex patterns like vessel networks and pathological features in deeper layers.

---

## Pros and Cons of Traditional CNNs

**Pros**:
- **Interpretability:** Explainability techniques like Grad-CAM allow us to visualize which retinal regions influence predictions. Simpler architectures provide more interpretability.
- **Lower Risk of Overfitting:** Traditional CNNs are less likely to memorize the training data.

**Cons**:
- **Lower Accuracy Ceiling:** More advanced architectures (like ResNet and EfficientNet) are generally more accurate.
- **Training instability:** Traditional CNNs are more prone to training difficulties in deeper networks.

---

## Explainability

Once we've trained our model, we will use Grad-CAM (Gradient-weighted Class Activation Mapping) to understand the relevance of different image features. This technique works by using the gradients flowing back from the final classification layer to weight the feature maps of the last convolutional layer, creating a heatmap that highlights which regions of the retinal image most strongly influenced the model's severity prediction. This visualization helps validate that our model is focusing on clinically relevant features like blood vessels, hemorrhages, and exudates rather than irrelevant background areas.


