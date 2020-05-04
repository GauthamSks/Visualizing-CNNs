# <div align='center'><i>Visualizing CNNs</i></dive>

<div align='center'>It’s often said that deep-learning models are “black boxes”: learning representations that are difficult to extract and present in a human-readable form. Although this is partially true for certain types of deep-learning models, it’s definitely not true for convnet's.Interpreting neural network's decision-making is an ongoing area of research, and it’s quite an important concept to understand. Neural networks are used in the real-world, so we can’t treat them like black boxes, we need to learn what they interpret, how they interpret, and what information each layer/channel in a neural network has learned.This interpretability matters because in order to build trust in intelligent systems and move towards their meaningful integration into our everyday lives, it is clear that we must build ‘transparent’ models that has the ability to explain why they predict what they predict.A solution to this problem is by visualizing the output of your deep learning model and see how its processing the given infromation. Here I shall demonstrate two of the techniques for visualizing what the convnet's has learned.</div>

The techniques are:
- <b><i>Saliency Mapping</i></b>
- <b><i>Class Activation Mapping</i></b>


## Saliency Mapping
- ### Saliency Map
- ### Guided Backpropagation

## Class Activation Mapping
<div align='center'>Class activation Mapping is a simple technique to get the discriminative image regions used by a CNN to identify a specific class in the image. In other words, a class activation map (CAM) lets us see which regions in the image were relevant to this class.This technique consists of producing heatmaps of “class activation” over input images. A “class activation” heatmap is a 2D grid of scores associated with a specific output class, computed for every location in an input image, indicating how important each location is with respect to the class considered. There are many implementations of this technique but here I shall be demonstrating the three most popular one mainly <i>CAM</i>, <i>Grad-CAM</i> and <i>Grad-CAM++</i>. </div>

- ### CAM
        This method was developed by Bolei Zhou in his paper "Learning Deep Features for  Discriminative Localization". Here he used a network architecture similar to Network in Network and GoogLeNet. The model largely consists of convolutional layers, and just before the final output layer he performa global average pooling on the convolutional feature maps and use those as features for a fully-connected layer that produces the desired output.Given this simple connectivity structure, we can identify the importance of the image regions by projecting back the weights of the output layer on to the convolutional feature maps compute a weighted sum of this feature maps to obtain our class activation maps.

<p align='center'><img src=./Files/CAM.png></p>

- ### Grad-CAM
        The major limitation of CAM is that the network architecture is restricted to have a global average pooling layer after the final convolutional layer, and then a linear (dense) layer. Unfortunately, this means we can’t apply this technique on existing networks that don’t have this structure. So as to overcome this issue R. Selvaraju preposed Grad-CAM in his paper "Grad-CAM: Visual Explanations from Deep Networks via Gradient-based Localization".Grad-CAM uses the gradient information flowing into the last convolutional layer of the CNN to assign importance values to each neuron for a particular decision of interest.
<p align='center'><img src=./Files/Grad-CAM.png></p>
        

- ### Grad-CAM++
        Though Grad-CAM explains the CNN based models prediction with fine-grained details of the predicted class, these methods have limitations - for example, they lack at localizing multiple occurrences of the same class. Even for single object images, Grad-CAM heatmaps fail to localize the entire region of the object. Thus Aditya Chattopadhyay preposed Grad-CAM++ in his paper "Grad-CAM++: Generalized Gradient-based Visual Explanations for Deep Convolutional Networks" which solves all the above-mentioned issues.

<p align='center'><img src=./Files/Grad-CAM++.png></p>