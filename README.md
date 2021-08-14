# Hand-Eyeball
A Snapchat filter/lens that spins an eyeball around the hand

## Motivation
Previously, I worked attaching a 3D model on the head. This time, I wanted implement a moving object on my hand.

## How is it done?
There were 3 things to achieve in this project:

1. Use a 3D animated object
2. Attaching the object on a single hand
3. Hide the object behind the hand

### 3D Animated Object
  To achieve the first objective, I had to look around for 3D objects that are animated as well. I tried famous websites like Free3D and TurboSquid, but I couldn't find a free animated model. I realise then that I cannot get a 3D animated model easily. However, I could not afford the time to create my own 3D model. This is something I will have to do in the future , now that I know it is not easy to get a 3D model; But I wont for now.
  
  Luckily Lens Studio, a friendly application to beginners, provide an animation script to rotate an object in circular pattern; The TweenTransform.js script. We can set the object to rotate and loop that animation using this script. All that's left for me to do is to correctly place it in the right position.

![TweenTransform.js screenshot](/ss1.png)

### Hand segmentation
  To achieve the second objective, I need lens studio to detect the user's hand and place the object to rotate around it's hand. Fortunately, Lens Studio, a friendly application to beginners, provide a template that consist of all the components required to perform Hand segmentation.
  
  Hand segmentation is the process locating a hand from a camera. Lens studio achieves this by using the Hand Segmentation Mask Camera. It generates a texture that shows what is the hand and not the hand that is used by objects visible in the Camera to detemine where some visuals should be shown or not shown (Confusing right? I just copied that from Lens studio documentation).
  
  So all I had to do , was to replace their model with mine.
  
  ![Project directory screenshot](/ss4.png)
  ![3D scene screenshot](/ss3.png)
  
### Hand Occluder
    Now if I run the project with just the Hand segmentation, it will look like the object is rotating infront of the hand. This is not what I want. I want it to rotate around the hand. Lens Studio still cannot achieve this with SnapML alone , so they, a friendly application for beginners, provide a Hand Occluder that hides the object when it's behind the hand
  

