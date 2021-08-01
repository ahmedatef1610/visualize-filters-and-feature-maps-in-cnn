# visualize-filters-and-feature-maps-in-convolutional-neural-networks (CNN)

### [visualization  code](https://nbviewer.jupyter.org/github/ahmedatef1610/visualize-filters-and-feature-maps-in-cnn/blob/master/Visualize_Filters_and_Feature_Maps_in_Convolutional_Neural_Networks.ipynb) 

we want to visualize filter (Feature detector) which use in convolutional layer and visualize feature map which output from convolutional layer

![ScreenShot_20210802000841](https://user-images.githubusercontent.com/39852784/127786711-6e53115a-1405-4461-ad2b-41ae944b1266.png)

---

### We need a model to visualize.

Instead of fitting a model from scratch, we can use a pre-fit prior state-of-the-art image classification model.

Keras provides many examples of well-performing image classification models developed by different research groups for the ImageNet Large Scale Visual Recognition Challenge, or ILSVRC. One example is the VGG-16 model that achieved top results in the 2014 competition.

This is a good model to use for visualization because it has a simple uniform structure of serially ordered convolutional and pooling layers, it is deep with 16 learned layers, and it performed very well, meaning that the filters and resulting feature maps will capture useful features. For more information on this model, see the 2015 paper “Very Deep Convolutional Networks for Large-Scale Image Recognition.”

---

### Visualize Filters

Perhaps the simplest visualization to perform is to plot the learned filters directly.

In neural network terminology, the learned filters are simply weights, yet because of the specialized two-dimensional structure of the filters, the weight values have a spatial relationship to each other and plotting each filter as a two-dimensional image is meaningful (or could be).

The first step is to review the filters in the model, to see what we have to work with.

The model summary printed in the previous section summarizes the output shape of each layer, e.g. the shape of the resulting feature maps. It does not give any idea of the shape of the filters (weights) in the network, only the total number of weights per layer

![image](https://user-images.githubusercontent.com/39852784/127786808-0693d4ea-95a2-4ba7-875b-6b7de97dc1a4.png)

---

### Visualize Feature Maps

The activation maps, called feature maps, capture the result of applying the filters to input, such as the input image or another feature map.

The idea of visualizing a feature map for a specific input image would be to understand what features of the input are detected or preserved in the feature maps. The expectation would be that the feature maps close to the input detect small or fine-grained detail, whereas feature maps close to the output of the model capture more general features.

In order to explore the visualization of feature maps, we need input for the VGG16 model that can be used to create activations. We will use a simple photograph of a bird. Specifically, a Robin, taken by Chris Heald and released under a permissive license.

![image](https://user-images.githubusercontent.com/39852784/127786861-5812eef3-0170-45d9-8aae-de626021a7b6.png)

Next, we need a clearer idea of the shape of the feature maps output by each of the convolutional layers and the layer index number so that we can retrieve the appropriate layer output.


![image](https://user-images.githubusercontent.com/39852784/127786871-3d9f299c-33e1-477c-ab45-6a3b6d5ff7ce.png)


---


