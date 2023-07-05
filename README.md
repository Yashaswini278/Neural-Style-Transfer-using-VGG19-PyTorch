# Neural-Style-Transfer-using-VGG19-PyTorch
The objective of this project is to create a new image that follows the content of one image and the style of another image. Neural style transfer technique using a pretrained VGG-19 convolutional neural network was used. The target image was initialized with random noise.
![before](images/Before.png)
## Feature Maps and Gram Matrices
The feature activation maps of content image and style image were obtained from the conv2d layers of the VGG19 network. The gram matrices were calculated for the style image from the feature maps. 
### Visualize Content Feature Maps and Content Gram Matrices
![content](images/content.png)
### Visualize Style Feature Maps and Style Gram Matrices
![style](images/style.png)
## Loss Function 
Conv1 layer and Conv4 layer were used for content matching 
<br> Conv0 layer to Conv4 layer was used for style matching
<br> The style loss gain factors used were [1, 0.5, 0.5, 0.4, 0.2, 0.1]
<br>The content loss was calculated as the MSE between content image feature maps and target image feature maps. 
<br>The style loss was calculated as the MSE between style gram matrices and target gram matrices. 
<br>The target image was trained on 1500 epochs to reduced the combined content loss and style loss using RMSprop optimizer. 
### Target Image Transformation every 100 epochs 
![transformation](images/Transformation.png)
### Content and Style Loss Curves
![loss](images/loss.png)
## Result: Final Stylized Version of Content Image 
![after](images/After.png)
