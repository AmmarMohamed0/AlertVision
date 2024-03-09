# AlertVision
## Importing Required Libraries
The code imports necessary libraries such as `torch`, `numpy`, `cv2`, `time`, `smtplib`, and relevant classes from the `ultralytics` and `supervision` packages for object detection and visualization.

## SMTP Connection Check
The function `check_smtp_connection()` checks if the SMTP server connection can be established using the provided email settings (`from_email`, `passwords`, etc.). If successful, it prints a success message, and if not, it prints an error message.

## Sending Email
The function `send_email()` is responsible for sending an email alert with the number of people detected. It uses the SMTP server initialized in the `check_smtp_connection()` function to send the email.

## ObjectDetection Class
This class encapsulates the functionality for object detection. It loads the YOLOv8 model, initializes necessary attributes, and defines methods for predicting, plotting bounding boxes, and running the detection process.

## `__call__` Method
This method is called when an instance of the `ObjectDetection` class is invoked. It starts a video capture loop where frames are captured from the specified video source, and object detection is performed on each frame. If the number of detected objects changes from the previous frame, an email alert is sent. The loop continues until the video ends or is manually interrupted.

## Displaying FPS
The code calculates and displays the frames per second (FPS) on each frame.

## Cleanup
After the video capture loop ends, the video capture is released, and OpenCV windows are destroyed. If an SMTP server was initialized, it is closed.
