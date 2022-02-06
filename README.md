# RealsenseObjectDetection
This project is an object detection module built using the Intel Realsense d435 Depth Camera and a MaskRCNN. The d435 takes 2 infared and 1 rgb image every 0.5 second, and these iamges are passed as inputs into a trained MaskRCNN. The MaskRCNN is able to detect all objects within the frame, along with the x,y,z (horizontal, vertical, depth) posiition of the object relative to the camera. In this repo, the position is simply printed out to the command line, but the position could also be sent in a ros publisher within a catkin workspace.


Dependencies:
  pip3 install opencv-python
  
  pip3 install pyrealsense2
  
How to Run:
  
  python3 measure_object_distance.py


How to Train:
  While not the most efficent or best way to train a new model, there is a google colab notebook that can be leveraged to train a new model. There are quite a few limitations to     this notebook, and the output model is a .h5 file which is not a .pb file so it must converted. 
  
  
  That being said, it is a good start but could be replaced with a better workflow: https://colab.research.google.com/github/pysource7/utilities/blob/master/Train_Mask_RCNN_(DEMO).ipynb
  
  
  To use the notebook, you will need to create your own training data. This can be done at https://www.makesense.ai/ where you will annoate your images, then save the annotations    as a .json file. The images and .json can be uploaded to the notebook to start training on your own dataset.
