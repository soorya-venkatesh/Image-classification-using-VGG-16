# Image-classification-using-VGG-16

## Dataset link: https://www.dropbox.com/s/rrrzckddlxsqs11/rvl-cdip.rar?dl=0

The data contains two files;images and labels. The label file list the images and their categories in the following format: path/to/the/image.tif, category     where the categories are numbered 0 to 15, 
in the following order:  
0 letter  
1 form    
2 email   
3 handwritten   
4 advertisement   
5 scientific report   
6 scientific publication   
7 specification   
8 file folder   
9 news article   
10 budget   
11 invoice  
12 presentation   
13 questionnaire  
14 resume  
15 memo  
### Model 1 summary:
1. Used VGG-16 pretrained network without Fully Connected layers and initialize all the weights with Imagenet trained weights.  
2. After the VGG-16 network without FC layers, add a new Conv block ( 1 Conv layer and 1 Maxpooling ), 2 FC layers and an output layer to classify 16 classes.   
3. Final architecture will be INPUT --> VGG-16 without Top layers(FC) --> Conv Layer --> Maxpool Layer --> 2 FC layers --> Output Layer 

### Model 2 summary:
1. Used VGG-16 pretrained network without Fully Connected layers and initialize all the weights with Imagenet trained weights.  
2. After the VGG-16 network without FC layers, used Conv layers only as a Fully connected layer. any FC layer can be converted to a CONV layer. This conversion will reduce the No of Trainable parameters in FC layers.[Reference](http://cs231n.github.io/convolutional-networks/#convert
)
3. Final architecture will be VGG-16 without FC layers(without top), 2 Conv layers identical to FC layers, 1 output layer for 16 class classification. INPUT --> VGG-16 without Top layers(FC) --> 2 Conv Layers identical to FC --> Output Layer

### Model 3 summary:
1. Used same network as Model-2 'INPUT --> VGG-16 without Top layers(FC) --> 2 Conv Layers identical to FC --> Output Layer' and trained only Last 6 Layers of VGG-16 network, 2 Conv layers identical to FC layers, 1 output layer.

