# Shooter Game

## 1. About the Game

Here, the player controls an immovable character in an environment with red balls spawning around them. The objective of the game is to shoot the red balls that act as targets.
Each hit is a point, there are no negative points for missing. 

![image](https://github.com/NathanFlex/XAI-Gaming/blob/main/ShooterGame/Explanations/test.png?raw=true)

## 2. Deep Learning Model Used

### YOLOv8

For this game, object detection was the primary goal, as the agent's job was to locate the position of the target to shoot it. We chose to employ [YOLOv8's](https://github.com/ultralytics/ultralytics)
object detection algorithm for our task.

### Training Details

The YOLOv8 model was trained using a custom dataset of 51 images collected from the game. The dataset was then further expanded to 153 images using image augmentations.
The dataset consists of 1 class labelled "ball".

## 3. Explanations Used

### a) Saliency Maps

Used to determine which pixels of the input image are most critical for the model when predicting the coordinates of the target. 
By computing the gradient of the output with respect to the input image, the saliency map highlights regions that most influence the model’s prediction

![image](https://github.com/NathanFlex/XAI-Gaming/blob/main/ShooterGame/Explanations/Saliency%20Map.png?raw=true)

### b) EigenCAM

A variation of Class Activation Maps (CAM) that uses principal component analysis (PCA) to generate a heat map indicating which regions of an image contribute the most to the model’s final decision.
For the shooter game, EigenCAM provides an intuitive way to visualize how the CNN layers are processing the image, showing what elements in the image the model considers important to predicting the position of the target.

![image](https://github.com/NathanFlex/XAI-Gaming/blob/main/ShooterGame/Explanations/EigenCAM1.png?raw=true)

![image](https://github.com/NathanFlex/XAI-Gaming/blob/main/ShooterGame/Explanations/EigenCAM2.png?raw=true)
