# Neural Image Caption Generation Using Pre-trained ResNet-101 and LSTM with Attention

In this notebook, I train an encoder-decoder model with attention mechanisms for the task of image captioning. The model is trained on the MS COCO dataset, utilizing Karpathy's split, which includes approximately 113,000 high-quality images in the training set. 

The encoder is a ResNet-101 convolutional neural network (CNN) pre-trained on large image datasets. While I did not fine-tune the CNN during training, the option to do so is available in the code below. The primary role of the CNN is to generate encoded representations of the image, extracting key features that are subsequently passed into the decoder for further processing.

The LSTM variant of recurrent neural networks (RNN) is chosen as the decoder. The attention mechanism is incorporated while decoding to determine how much attention should be placed on each region in the encoded image. This helps address the main issue with RNNs: their difficulty in handling long sequences of input, especially in cases where important information is spread out across a large number of pixels in the image.

The ADAM optimizer is used to update the model’s weights, offering robust optimization by combining the benefits of adaptive learning rates and momentum. I utilize a learning rate scheduler to dynamically adjust the learning rate during training, helping to achieve more efficient convergence and avoid overshooting minima.


The model I trained reached a top-5 validation accuracy of 76.57% and top-10 validation accuracy of 83.80%. An example image with a generated caption can be seen at the bottom of the notebook. 
