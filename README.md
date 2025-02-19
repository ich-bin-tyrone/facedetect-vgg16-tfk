# 📸 Face Tracker  

## 📝 Description  
This repository contains a face-tracking application that captures facial images, trains a model using the **VGG16** architecture, and tests face detection in real-time.  

## 📦 Requirements  

Ensure you have the following installed:  

- Python **3.x**  
- Jupyter Notebook  
- TensorFlow  
- OpenCV  
- Albumentations  

You can install all required packages using:  
```bash
pip install tensorflow opencv-python albumentations
```

## 🔧 How to Use the Application  

### **1️⃣ Download the Repository**  
Clone or download the repository to your local machine:  
```bash
git clone <repository_link>
cd <repository_directory>
```

### **2️⃣ Prepare the Data Folders**  
Before starting, delete all the photos and labels in the `data` and `aug_data` folders to ensure a fresh start.  

### **3️⃣ Capture Facial Images**  
Run the following command to start capturing facial images using your webcam:  
```bash
jupyter notebook data.ipynb
```
- This will prompt the webcam to capture photos of your face.
- You will manually annotate the images using bounding boxes and properly labeling them.
- JSON labels will be generated afterward containing the information on the annotations.  

### **4️⃣ Train the Model**  
Start the model training process by running:  
```bash
jupyter notebook model.ipynb
```
- Images will be sorted into `train`, `test`, and `val` folders.  
- Augmentation will be applied using **Albumentations**, with the results stored in `aug_data`.  
- After training, the model will be saved as `facetracker_vgg16.h5` in your **Desktop directory**.  

### **5️⃣ Test the Face Detection App**  
To test face detection using the trained model, run:  
```bash
jupyter notebook model_test.ipynb
```
- This will allow you to validate the face-tracking functionality in real time.  

---

## 📂 Folder Structure  
```plaintext
├── aug_data/         # Augmented images generated using Albumentations  
├── data/             # Contains images and JSON files with bounding box & class info  
├── logs/             # Stores callback logs during model training  
├── data.ipynb        # Captures facial images and generates labels  
├── model.ipynb       # Trains the VGG16-based face tracking model  
├── model_test.ipynb  # Tests the trained model for face detection  
├── README.md         # Project documentation  
├── .DS_Store         # macOS system file (safe to ignore)  
```


---

## 💡 Contributing  
Feel free to contribute by submitting **issues** or **pull requests**! 😊  
