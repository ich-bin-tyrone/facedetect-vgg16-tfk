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
- Labelme  

You can install all required packages using:  
```bash
pip install tensorflow opencv-python albumentations labelme
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

### **4️⃣ Annotate the Images**  
Use `labelme` to annotate the images by following these steps:  

#### **Start the Annotation Tool**  
Run the command:  
```bash
labelme
```
This will open the Labelme interface.  

#### **Load the Images**  
- Navigate to the `data/images/` folder where your captured images are stored.  
- Click **File** → **Change Output Directory** and select `data/labels/`.  
- Click **File** → **Save Automatically** to ensure annotations are saved automatically.  

#### **Annotate Each Image**  
- Click **Edit** → **Create Rectangle** to start drawing bounding boxes.  
- Manually draw a box around your face for each image.  
- When prompted, enter the class name (e.g., `"face"`) and click **OK**.  

#### **Navigating Through Images**  
- Press `D` on your keyboard to move to the next image.  
- If an image **does not contain a face**, **skip it** without annotating.  

Once completed, `labelme` will generate JSON files in `data/labels/`, containing the bounding box coordinates and class labels.  

### **5️⃣ Train the Model**  
Start the model training process by running:  
```bash
jupyter notebook model.ipynb
```
- Images and labels will be sorted into `train`, `test`, and `val` folders.  
- Augmentation will be applied using **Albumentations**, with the augmented images stored in `aug_data/{train,test,val}/images` and their corresponding labels saved in `aug_data/{train,test,val}/labels`.
- After training, the model will be saved as `facetracker_vgg16.h5` in your **Desktop directory**.  

### **6️⃣ Test the Face Detection App**  
To test face detection using the trained model, run:  
```bash
jupyter notebook model_test.ipynb
```
- This will allow you to validate the face-tracking functionality in real time.

  ![Demo](test.gif)

  ![Demo](test-speed.gif)

---

## 📂 Folder Structure  
```plaintext
├── aug_data/         # Augmented images generated using Albumentations  
│   ├── train/       # Augmented training data  
│   │   ├── images/   # Augmented training images  
│   │   ├── labels/   # Corresponding JSON labels  
│   ├── test/        # Augmented test data  
│   │   ├── images/   # Augmented test images  
│   │   ├── labels/   # Corresponding JSON labels  
│   ├── val/         # Augmented validation data  
│   │   ├── images/   # Augmented validation images  
│   │   ├── labels/   # Corresponding JSON labels  
├── data/            # Raw captured images and annotations
│   ├── images       # Original directory containing the images before the train-test-val split
│   ├── labels       # Original directory containing the labels before the train-test-val split
│   ├── train/       # Training data  
│   │   ├── images/   # Raw training images  
│   │   ├── labels/   # JSON annotations from Labelme  
│   ├── test/        # Test data  
│   │   ├── images/   # Raw test images  
│   │   ├── labels/   # JSON annotations from Labelme  
│   ├── val/         # Validation data  
│   │   ├── images/   # Raw validation images  
│   │   ├── labels/   # JSON annotations from Labelme  
├── logs/            # Stores callback logs during model training  
├── data.ipynb       # Captures facial images and generates labels  
├── model.ipynb      # Trains the VGG16-based face tracking model  
├── model_test.ipynb # Tests the trained model for face detection  
├── README.md        # Project documentation  
├── .DS_Store        # macOS system file (safe to ignore)  


---

## 💡 Contributing  
Feel free to contribute by submitting **issues** or **pull requests**! 😊  

