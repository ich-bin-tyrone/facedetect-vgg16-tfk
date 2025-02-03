# Face Tracker

## Description
This repository contains a face tracking application that captures facial images, trains a model using VGG16 architecture, and tests face detection in real-time.

## Getting Started

### Prerequisites
- Python 3.x
- Jupyter Notebook
- TensorFlow
- OpenCV
- Albumentations

Make sure to install the required libraries:
```bash
pip install tensorflow opencv-python albumentations
```

### Installation
1. **Download the Repository**  
   Clone or download the repository to your local machine.

2. **Prepare the Data Folders**  
   Delete all the photos and labels in the `data` and `aug_data` folders to start fresh.

3. **Capture Facial Images**  
   Run `data.ipynb`:
   ```bash
   jupyter notebook data.ipynb
   ```
   This will prompt the webcam to capture photos of your face and generate corresponding JSON labels.

4. **Train the Model**  
   Run `model.ipynb`:
   ```bash
   jupyter notebook model.ipynb
   ```
   - This will sort the images into `train`, `test`, and `val` folders.
   - It will augment the images using Albumentations and store them in `aug_data`.
   - After training, the model `facetracker_vgg16.h5` will be saved to your Desktop.

5. **Test the Face Detection App**  
   Run `model_test.ipynb`:
   ```bash
   jupyter notebook model_test.ipynb
   ```
   This will allow you to test the face detection functionality using the trained model.

## Contributing
Contributions are welcome! Feel free to fork the repository and submit pull requests.

---
Feel free to modify the repository URL and license details accordingly.

