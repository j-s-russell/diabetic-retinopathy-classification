# Modern Deep Learning Methods

While traditional CNNs achieve decent performance, they face several key limitations that prevent optimal results for diabetic retinopathy classification. Their inability to train very deep networks due to vanishing gradients restricts their capacity to learn complex features needed to distinguish between subtle severity levels. Traditional CNNs also lack the parameter efficiency and attention mechanisms that help focus on diagnostically important retinal regions, making them less effective at handling class imbalance and detecting rare severe cases. Additionally, they struggle with the multi-scale nature of retinal pathology, where lesions range from tiny microaneurysms to large hemorrhages. These limitations drive the need for more advanced architectures.

---

## Selected Methods and Rationale

We selected ResNet-50 and EfficientNet-B3 as our primary modern architectures based on their complementary strengths and proven performance in medical imaging applications.

**ResNet-50**
- Deep convolutional network with 50 layers using residual blocks and skip connections that enable training very deep networks by learning residual mappings instead of direct feature mappings
- **Pros:** Proven track record in medical imaging with the ability to learn complex hierarchical features for subtle pattern detection
- **Cons:** Higher computational and memory requirements, less parameter-efficient compared to other architectures

**EfficientNet-B3**
- Compound-scaled architecture that systematically balances network depth, width, and resolution
- **Pros:** Great parameter efficiency leads to great accuracy relative to network size, built-in channel attention helps focus on diagnostically relevant features
- **Cons:** Architecture is complex, so it's harder to interpret and modify