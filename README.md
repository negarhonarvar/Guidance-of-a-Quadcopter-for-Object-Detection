# Guidance of a Quadcopter for Object Detection
<p align = "center">
   <img src="https://github.com/user-attachments/assets/48067e55-711a-434c-b238-9cb7c6892f14" width = "400" >
</p>

## Prerequisites 📋
To successfully run the codes in this repository, you need to install:

    Webots R2023b
    keras  
    cv2
    PIL
    
And to load the environment, you need to open .wbt file in webots :

    mavic_2_pro.wbt

## Implementation
We aim to design a controller for a quadcopter in order to control its flight over a number of boxs in the following environment:

<p align = "center">
  <img src="https://github.com/user-attachments/assets/d18c1414-8f01-4bf2-8b09-fd9b29ce7dde" width = "400" >
</p>

Each box is labeled with one image from MNIST fashion dataset and at each run we determain a 'target label' which corresponds to the clothing item we want to detect. When our robot flies over this boxes, it is supposed to take images from this boxs and , using a cnn , determine the clothing item in captured image. If the output of the cnn doesn't match with the target label then aour robot continues fliyng and visits other boxs but if the labels match then it should land next to the box with target clothing item and turn on its front LED's.
## Controller
I started coding the controller with trying diffrent values of speed ,height and angles for flying and capturing images and finding the optimal values. Once the values were found during a time consuming proccess of test and failures the controller was ready for action. For having a better understanding of the controller visit webots documentation of quadcoptor controller and commands to enable its camera and LED's.
## CNN
Since the MNIST fashion dataset includes low-resolution images ,we had to apply a number of filters on the caputerd images before feeding it to our cnn. Since the edges were not quite obvious, our model frequency mistook all fashion items with bags due to their curvy shape. To address this issue we increased the contrast which made edges more distinguish and sharp along with a number of other filtesr which helped our model to predict labels correctly.

### Final Result

https://github.com/user-attachments/assets/e92797eb-8e1d-4f8b-aa8b-a2a283a40b5e


