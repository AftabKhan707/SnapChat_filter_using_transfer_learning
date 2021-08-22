# Snapchat-Filter-using-Transfer-Learning
Snapchat Filter using the concept of Transfer Learning

In this project the concept of **Transfer Learning** is used to train the model which is further used to place filters over the face.

So i used the knowledge gained by the model facenet_keras.h5(which encodes the given image into 128x1 dimension) to detect the facial features/keypoints.

**DATA**

dataset used :  Helen Dataset 

Data preprocessing : the available dataset consist of face images, each having a seperate .txt file consisting the 
facial co-ordinates.

The dataset is preprocessed which include resizing and storing the images and coordinates into .npy file.

The preprocessed data is available at : https://www.kaggle.com/yash88600/kernel75d7c60e9a 

**MODEL**


specification of facenet_keras.h5 model :

                         input shape : (160x160x3)
                         output shape : (128x1)
                         purpose : to encode the given image into 128x1 dimension 
                                        
changes made to the above model while keeping the weights same:

                         input shape : (200x200x3)
                         output shape: (388,1) ((x,y) coordinates of 194 keypoints)
                         purpose : to detect facial features/keypoints
                                     
The layers with name block8,avgpool,Dropout were only allowed to train while the weights of other layer were kept same.

The model was then trained on the **HELEN DATASET**- http://www.ifp.illinois.edu/~vuongle2/helen/

For training:
                        
                         training data size: 2000 images (all were converted to numpy array(img.npy))
                         optimizer used : Adam Optimizer
                         Learning Rate: 0.0001
                         Loss function: mean_squared_error
                         No of epochs: 500
                         batch_size: 32
                         
                         
After training basic maths is used to extract the required part from the image and embed filter over it

 **results:**


https://user-images.githubusercontent.com/52177580/130363926-1e62bd5a-6062-466e-a050-b81f700cbcf6.mp4



https://user-images.githubusercontent.com/52177580/130364012-977c513e-b944-4d00-9188-ef34d98a1336.mp4





**Note: The trained model is also provided**

