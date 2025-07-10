# Traditional Methods (Basic CNN)

---

```{admonition} Note
:class: info
If you are unfamiliar with deep learning with neural networks, please review this [AIML.com article](https://aiml.com/what-is-the-basic-architecture-of-an-artificial-neural-network-ann/) first.
```

## Baseline Model

Our first model will be a traditional convolutional neural network (CNN), which is a neural network architecture that utilizes convolutional layers to automatically learn distinct features from images. Convolutions are mathematical operations which slide a filter over an input (such as an image) to extract local patterns like edges, textures, or shapes. CNNs revolutionalized image classification as they did not require manual feature engineering - these features were learned automatically and were much more informative. Our goal is to train a CNN to learn specific features, such as hemorrhages or exudates, and map them to different severity levels of DR.

Our CNN will have a straightforward architecture consisting of multiple convolutional layers followed by max pooling operations (taking the maximum of nearby pixels), [batch normalization](https://aiml.com/what-is-the-difference-between-a-batch-and-an-epoch/), and fully connected layers for classification. The early convolutional layers will start by identifying low-level edges and textures, eventually building up to more abstract and complex patterns in deeper layers.

:::{iframe} https://www.youtube.com/embed/HGwBXDKFk9I
:width: 100%
:::

---

## Pros and Cons of Traditional CNNs

**Pros**:
- **Interpretability:** Explainability techniques like [Grad-CAM](https://arxiv.org/abs/1610.02391) allow us to visualize which retinal regions influence predictions. Simpler architectures provide more interpretability.
- **Lower Risk of Overfitting:** Traditional CNNs are less likely to memorize the training data.

**Cons**:
- **Lower Accuracy Ceiling:** More advanced architectures (which we will explore in the next chapter) are generally more accurate.
- **Training instability:** Traditional CNNs are more prone to training difficulties in deeper networks.

---

## Explainability

Once we've trained our model, we will use [Grad-CAM](https://arxiv.org/abs/1610.02391) (Gradient-weighted Class Activation Mapping) to understand the relevance of different image features. This technique works by using the gradients flowing back from the final classification layer to weight the feature maps of the last convolutional layer, creating a heatmap that highlights which regions of the retinal image most strongly influenced the model's severity prediction. This visualization helps validate that our model is focusing on clinically relevant features rather than irrelevant background areas.


