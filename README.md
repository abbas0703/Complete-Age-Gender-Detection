# Complete-Age-Gender-Detection
## Age and Gender Detection using OpenCV and Deep Learning

This project uses OpenCV's deep learning (DNN) module to detect faces in an image or video and classify the detected faces by age and gender using pre-trained models. The model can detect age ranges and gender using deep neural networks (DNN) trained on appropriate datasets.

## Features

- Detect faces in images or live video streams.
- Classify the detected faces as either 'Male' or 'Female.'
- Predict the age range of the detected faces.
- Real-time detection using a webcam.

## Dependencies

Before running the project, make sure you have installed the following libraries and packages:

- Python 3.x
- OpenCV (cv2)
- argparse (for command-line argument parsing)

You can install the required dependencies using:

```bash
pip install opencv-python opencv-python-headless
```

## Model Files

All the necessary model files are included in this repository. These files include:

1. **Face detection model (Caffe)**:
   - `opencv_face_detector.pbtxt`
   - `opencv_face_detector_uint8.pb`
   
2. **Age detection model**:
   - `age_deploy.prototxt`
   - `age_net.caffemodel`

3. **Gender detection model**:
   - `gender_deploy.prototxt`
   - `gender_net.caffemodel`

You do not need to download them separately. Just clone this repository and everything will be available.

## How it Works

### 1. Face Detection
The face detection is handled using OpenCV's DNN module. The `highlightFace` function is responsible for detecting faces in the input image or video.

### 2. Age and Gender Prediction
After detecting the face, the project uses pre-trained deep learning models to predict the age and gender of the detected face. The face is cropped and resized to match the input dimensions of the age and gender detection models.

## Code Explanation

- The script first loads the pre-trained models for face, age, and gender detection.
- It uses `cv2.VideoCapture()` to either open an image or capture video from the webcam.
- The function `highlightFace` detects the faces in the frame.
- For each detected face, the face region is cropped, and a blob is created using `cv2.dnn.blobFromImage()`. This blob is passed to the age and gender networks.
- The predicted age and gender are displayed on the image using `cv2.putText()`, and the processed frames are shown using `cv2.imshow()`.

## Usage

You can run the project in two ways: using an image file or using a webcam.

### 1. Run with an Image
To detect age and gender from an image, use the following command:

```python
python detect_age_gender.py --image <path_to_image>
```

### 2. Run with Webcam
To detect age and gender using your webcam:

```python
python detect_age_gender.py
```

This will open a window showing the live feed from your webcam, with detected faces, ages, and genders.

## How to Modify

- **Adjust Confidence Threshold**: You can modify the `conf_threshold` in the `highlightFace` function to adjust the face detection sensitivity. Increasing the threshold will make the detection stricter, whereas lowering it will make it more lenient.

- **Extend Age Range**: You can modify the `ageList` in the script to include additional age ranges or make it more granular. This allows you to customize the age classification as per your needs.

## Output
The output will display the detected face with a rectangle, along with the predicted age and gender above the face.

## Example:
For a given image or video frame, the system will display something like this:
```bash
Gender: Male
Age: 30 years

```

## License

This project is licensed under the MIT License. You can find the full text of the license [here](LICENSE).




