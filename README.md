Real-Time Face Blurring with OpenCV (Python)

This project demonstrates how to use OpenCV (Python) to access your device's camera and apply a Gaussian blur effect to any detected faces in real-time. This can be useful for privacy applications where you want to obfuscate faces in a video stream.

Code:
The code for this project is provided in the included Jupyter Notebook file (face_blurring.ipynb).

Instructions:

Install OpenCV:
Make sure you have OpenCV installed. You can install it using pip on command line:
pip install opencv-python

Run the Jupyter Notebook:
Open a Jupyter Notebook and open the face_blurring.ipynb file. Run the code cells sequentially.

Explanation:
The code performs the following steps:

Imports:
cv2: OpenCV library for image processing.
Face Detection:
Loads a pre-trained face detection classifier (haarcascade_frontalface_default.xml) that identifies faces in images.
Webcam Access:
Opens the default webcam (cap = cv2.VideoCapture(0)) to capture video frames.
Real-Time Processing:
Uses a while loop to continuously read frames from the webcam.
Frame Conversion:
Converts each frame to grayscale (gray_frame) for better face detection performance.
Face Detection:
Uses the classifier to find faces in the grayscale frame (faces = face_cascade.detectMultiScale(...)).
Face Blurring:
Iterates through each detected face ((x, y, w, h) coordinates):
Extracts the region of interest (ROI) containing the face (face_roi).
Applies a Gaussian blur effect to the ROI (blurred_face = cv2.GaussianBlur(...)). This blurs the pixels, obscuring the details of the face.
Replaces the original face ROI with the blurred version in the main frame (frame[y:y+h, x:x+w] = blurred_face).
Display and Exit:
Displays the blurred frame with cv2.imshow('Blurred Faces', frame).
Waits for a key press (cv2.waitKey(1)) to allow for user exit. Pressing Enter (key code 13) will terminate the program.
Releases the webcam capture and cleans up resources (cv2.destroyAllWindows(), cap.release()).

Additional Notes:

You can adjust the blur parameters ((99, 99), 20) in the cv2.GaussianBlur function to fine-tune the blurring effect.
Explore other OpenCV functions for further image processing tasks.
Refer to the OpenCV documentation https://docs.opencv.org/4.x/ for more details on face detection and other functionalities.
