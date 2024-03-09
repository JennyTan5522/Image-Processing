The study purpose is to design and implement a perspective transformation algorithm 
using image processing techniques to generate a top-down view of a scene. The algorithm include: 

Image Preprocessing: Develop preprocessing techniques to enhance the 
input image, such as noise reduction, contrast adjustment, and edge 
enhancement. These preprocessing steps aim to improve the accuracy and 
quality of subsequent processing.

Cross Point and/or Line Detection: Detecting cross 
points and/or lines in the image. These points or lines will serve as control 
points for the perspective transformation. Consider techniques like Hough 
transform, line segment detection, or corner detection to identify suitable 
cross points or lines in the image.

Floor Detection: Automatically detect the floor or 
ground plane in the image. 

User Interaction: A user-friendly interface that allows users to 
manually select the cross points or lines detected in the previous step. Users 
should have the flexibility to choose the most appropriate control points for 
the perspective transformation.

Perspective Transformation: Perspective transformation 
algorithm using the chosen control points or lines. This algorithm should map 
the perspective of the scene to a top-down view by rectifying distortions 
caused by the camera angle.
