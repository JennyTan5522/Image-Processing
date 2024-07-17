About:
Perspective transformation is important in image processing area because it aids in rectifying those distortions image. This results in optimising training data, especially for data augmentation purposes.

Objectives:
- To develop image perspective transformation system
- To compare effects of different image enhancement methods on the detected edge
- To compare different interpolation method for perspective transformation in OpenCV library
- To compare results of perspective transformation on different libraries

Dataset Description:
- Based on two categories: Natural Images and Documents
- The natural image dataset encompasses a diverse collection of 6899 images, each belonging to one of eight distinct categories, which include airplanes, cars, cats, dogs, flowers, fruits, motorbikes, and people. These images are in RGB format, with each pixel represented by three colour components within the range of 0 to 255 [https://www.kaggle.com/datasets/prasunroy/natural-images].
- The document datasets used for perspective transformation encompass two separate categories: ancient documents [https://www.kaggle.com/datasets/alexstrangejkbhc/image-recognition-of-ancient-documents] and FUNSD polygon documents [https://www.kaggle.com/datasets/danngalann/funsd-polygon], both of which are sourced from Kaggle. The ancient documents dataset comprises Chinese ancient text, whereas the FUNSD polygon document dataset comprises a collection of noisy scanned documents.

---------------------------------------------------------------------------------------------------------------------------------

Comparison of each open-source libraries:
- OpenCV
- Scikit-image (skimage)
- Pillow (PIL)

---------------------------------------------------------------------------------------------------------------------------------

Process Flow:

The system that begins with the acceptance of an input image, serving as the foundational element for all subsequent processes. Subsequently, the user need to define critical parameters, including image enhancement methods, the choice of image processing library, interpolation methods, and rotation angles and axes where necessary. Following the input stage, image preprocessing is initiated to optimise the input image for subsequent transformations. This process includes the application of Gaussian smoothing to reduce noise, conversion to grayscale for simplification, and the utilisation of an average filter for additional image smoothing.

A pivotal point in the system's flow is the examination of the user's choice of image enhancement methods. If contrast enhancement or both contrast and edge enhancement are selected, the system proceeds with contrast enhancement as the first enhancement step, subsequently evaluating whether edge enhancement should be applied. If "both" enhancements are chosen, edge enhancement follows contrast enhancement. Conversely, if the user solely selects edge enhancement, the system directly proceeds to this step and applies Otsu Binarization on the enhanced image.

Following image preprocessing and enhancement, the Canny edge detection algorithm is employed to identify significant edges within the preprocessed image. This step is of paramount importance for object identification and subsequent transformation. The system then employs a closing morphological operation on the detected edges to refine their continuity and fill gaps, further enhancing the edge detection process. Subsequently, the system identifies the most significant contour within the processed image, which may represent an object of interest. Depending on whether this contour is determined to be rectangular or not, the system either approximates it as a rectangle to obtain precise corner coordinates or draws a rectangular bounding box around it, subsequently extracting the bounding box's corner coordinates.

Floor detection is a critical stage in the system flow, entailing the identification of a reference floor area. This is accomplished through the identification of the colour with the largest area in the image, excluding regions identified as objects. A mask for the floor is generated through thresholding with this identified colour, and the contour delineating the floor is detected within the generated mask. A bounding box is drawn around the floor, and the system evaluates the area of the detected floor to determine whether it covers more than 90% of the image (indicating a top-down view) or less (indicating a side view).

For visual reference, the system displays the input image with either a bounding box or contour around the detected object. The system subsequently allows and checks if the user would like to redefine control points. If affirmative, the user provides new control points, and the system updates the displayed image with the revised information. Following this, the system calculates the output coordinates of the detected object in the transformed image. In the absence of control point redefinition, the system proceeds directly to calculate the output coordinates. 

The final stage in the system's flow involves perspective transformation. This critical operation encompasses the acquisition or calculation of the transformation matrix, encapsulating the transformation parameters. 

---------------------------------------------------------------------------------------------------------------------------------

Conclusion: The results show that the perspective transformation generated by OpenCV outperforms other libraries. 
