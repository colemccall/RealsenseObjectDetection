# RealsenseObjectDetection
An object detection module created for use in the Northwest Nazarene University Rocksat-X 2022 Research Project. Using an Intel Realsense d435 Depth Camera, a MaskRCNN can be trained to detect objects that will be launched in space during the Rocksat-X Launch.


### Developed by: 
- Cole McCall, Undergraduate Computer Science Research Assistant, Northwest Nazarene University, colemccall@nnu.edu, 262-597-5651


### What you need:
  - Hardware
    * Intel Realsense d435 Depth Camera
  - Software
    * Visual Studio Code
    * Python
  - Python Dependencies
    * `pip3 install opencv-python`
    * `pip3 install pyrealsense2`
   
### How it works:
The d435 takes 2 infared and 1 rgb image every 0.5 second, and these images are passed as inputs into a trained MaskRCNN. The MaskRCNN is able to detect all objects within the frame, along with the x,y,z (horizontal, vertical, depth) posiition of the object relative to the camera. In this repo, the position is simply printed out to the command line, but the position could also be sent in a ros publisher within a catkin workspace.
  - Running the program
    * `python3 measure_object_distance.py`
  - Training a New Model
    * While not the most efficent or best way to train a new model, there is a google colab notebook that can be leveraged to train a new model. There are quite a few limitations to     this notebook, and the output model is a .h5 file which is not a .pb file so it must converted. 
    * That being said, it is a good start but could be replaced with a better workflow: https://colab.research.google.com/github/pysource7/utilities/blob/master/Train_Mask_RCNN_(DEMO).ipynb
  - Creating Training Data
    * To use the notebook, you will need to create your own training data. This can be done at https://www.makesense.ai/ where you will annoate your images, then save the annotations    as a .json file. The images and .json can be uploaded to the notebook to start training on your own dataset.
  - Converting
    * Some of the code may need to be adjusted in the k2tf_convert.py but this repo will show you how to convert a model.h5 to model.pb so that it can be ran using the realsense camera: https://github.com/bitbionic/keras-to-tensorflow.git
  - Alternative Options
    * Another way to train would be by following this repo: https://github.com/soumyaiitkgp/Custom_MaskRCNN.git. Here, you clone the repo, then go to samples/custom. In the custom folder, there is a seperate readme that explains how to train and test a new model, along with all the files to do so.

