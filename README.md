# <div align='center'><i>Visualizing CNNs</i></dive>

<div align='left'>It’s often said that deep-learning models are “black boxes”: learning representations that are difficult to extract and present in a human-readable form. Although this is partially true for certain types of deep-learning models, it’s definitely not true for convnet's.Interpreting neural network's decision-making is an ongoing area of research, and it’s quite an important concept to understand. Neural networks are used in the real-world, so we can’t treat them like black boxes, we need to learn what they interpret, how they interpret, and what information each layer/channel in a neural network has learned.This interpretability matters because in order to build trust in intelligent systems and move towards their meaningful integration into our everyday lives, it is clear that we must build ‘transparent’ models that has the ability to explain why they predict what they predict.A solution to this problem is by visualizing the output of your deep learning model and see how its processing the given infromation. Here I shall demonstrate two of the techniques for visualizing what the convnet's has learned they are <b><i>Saliency Mapping</i></b> and <b><i>Class Activation Mapping</i></b>.</div>

## Saliency Mapping
Saliency map is an image that shows each pixel's unique quality. The goal of a saliency map is to simplify and/or change the representation of an image into something that is more meaningful and easier to analyze. The Saliency map shows which pixels need to be changed the least to affect the class score the most. One can expect that such pixels correspond to the object location in the image. There are many implementations of this technique but here I shall be demonstrating the two most popular ones mainly <b><i>Saliency Map</i></b>, <b><i>Guided Backpropagation</i></b> .

<p align='center'><img src=./Files/Saliency-Mapping.png></p>

## Class Activation Mapping
Class activation Mapping is a simple technique to get the discriminative image regions used by a CNN to identify a specific class in the image. In other words, a class activation map (CAM) lets us see which regions in the image were relevant to this class.This technique consists of producing heatmaps of “class activation” over input images. A “class activation” heatmap is a 2D grid of scores associated with a specific output class, computed for every location in an input image, indicating how important each location is with respect to the class considered. There are many implementations of this technique but here I shall be demonstrating the three most popular ones mainly <b><i>CAM</i></b>, <b><i>Grad-CAM</i></b> and <b><i>Grad-CAM++</i></b>.

<p align='center'><img src=./Files/CAM-Mapping.png></p>

## References

- <a href="https://arxiv.org/abs/1312.6034">Deep Inside Convolutional Networks: Visualising Image Classification Models and Saliency Maps by Karen Simonyan</a>
- <a href="https://arxiv.org/abs/1412.6806">Striving for Simplicity: The All Convolutional Net by Jost Tobias</a>
- <a href="https://arxiv.org/abs/1512.04150">Learning Deep Features for Discriminative Localization by Bolei Zhou</a>
- <a href="https://arxiv.org/abs/1610.02391">Grad-CAM: Visual Explanations from Deep Networks via Gradient-based Localization by Ramprasaath R. Selvaraju</a>
- <a href="https://arxiv.org/abs/1710.11063">Grad-CAM++: Generalized Gradient-based Visual Explanations for Deep Convolutional Networks by Aditya Chattopadhyay</a>
- <a href="https://www.amazon.in/Deep-Learning-Python-Francois-Chollet/dp/1617294438">Deep Learning with Python by François Chollet</a>
- <a href="https://github.com/jacobgil/keras-grad-cam">keras-grad-cam</a>