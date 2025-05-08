# Face_Based_Distance_Estimation
Face-Based Distance Estimation using OpenCV
This project demonstrates how to estimate the distance of a human face from a camera using image processing techniques in OpenCV. Instead of using any deep learning model, this approach leverages the mathematical relationship between real-world dimensions and image coordinates using a reference image and Haar Cascade classifier for face detection.

📌 Project Objective
Estimate the distance (in cm) between the camera and a person based on the apparent width of the person's face in a captured image.

🔧 How It Works
1. Reference Image for Calibration
A reference image with a known distance (e.g., 76.2 cm) and actual face width is used.

Using this image, the focal length is calculated using the formula:

Focal Length
=
Width in pixels
×
Known Distance
Real Width
Focal Length= 
Real Width
Width in pixels×Known Distance
​
 
2. Distance Estimation
For any test image, detect the face width in pixels.

Estimate the distance using the formula:

Distance
=
Real Width
×
Focal Length
Width in pixels
Distance= 
Width in pixels
Real Width×Focal Length
​
 
3. Face Detection
Uses Haar Cascade classifier to detect faces and calculate bounding boxes.

📌 Key Functions
Focal_Length_Finder(measured_distance, real_width, width_in_rf_image)

Distance_finder(Focal_Length, real_face_width, face_width_in_frame)

face_data(image) - detects the face and returns width in pixels.

🧪 Requirements
Python 3.x

OpenCV

NumPy

Google Colab or Jupyter environment

Haar Cascade file 

🖼️ Sample Output

The test images show distance labels ("near"/"far") based on thresholds (e.g., 100 cm).

Output includes the bounding box around the face and a printed estimated distance.

⚠️ Troubleshooting

Face Not Detected: Ensure the XML file is loaded correctly and lighting/angle of the image is proper.

Distance is Zero: Likely due to face detection failure; use larger/clearer images.

