# What is DeepDream?
Simply we take an image and then ouput 'Dreams' or hallucinogenic effects on the image. 
![image](https://4.bp.blogspot.com/-FPDgxlc-WPU/VYIV1bK50HI/AAAAAAAAAlw/YIwOPjoulcs/s1600/skyarrow.png)
![Image](https://3.bp.blogspot.com/-R15_fyB-ZpE/VYIV-Uu9iwI/AAAAAAAAAl4/o3heQNGpVRU/s1600/Funny-Animals.png)

The DeepDream algorithm effectively is asking a pre-trained CNN to take a look at the image, identify patterns you recognise and amplify it.<br>
It uses representations learned by CNNs to produce these hallucinogenic or 'trippy' images. 

• • • <br>
## The DeepDream algorithm High level
- In Deep Dream, instead of maximising a class output, we let the network decide.
- We feed it an input image and allow the network to analyse the image
- We then choose a layer and ask the network to amplify or enhance whatever it detected.
- Remember each layer deals with different features (high-level, low level) so the complexity of the pattern depends on these features. E.g. low level features look like brushes or strokes.

![image](https://3.bp.blogspot.com/-4Uj3hPFupok/VYIT6s_c9OI/AAAAAAAAAlc/_yGdbbsmGiw/s1600/ibis.png)

## The DeepDream algorithm Low level
- Get an input image
- Load a pertained model (VGG16, InceptionV3 etc.) to be used as a feature extractor
- Calculate loss which is the sum of the activations between the chosen layers. We also normalise at each layer so contributions from each layer are ‘equal’
- We use gradient ascent to do this, unlike gradient descent where we’re trying to find the local minima, gradient ascent tries to maximise its loss which allows the network to find less meaningful patters.
- Apply this at different scales (sizes) so that the patterns don’t occur at the same granularity
