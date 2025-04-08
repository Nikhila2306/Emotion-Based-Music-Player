# 🎵 Emotion-Based Music Player

Emotion based music recommendation system which detects your emotions in real time using facial expressions and hand gestures, then suggests music that matches your mood. Built with Python, OpenCV, MediaPipe, Keras, and Streamlit, this project bridges computer vision and deep learning to deliver a personalized musical experience.

---

## 🚀 **Features**

- 🔍 **Real-time emotion detection** using webcam input
- 🎭 **Facial and hand landmark tracking** with MediaPipe
- 🧠 **Custom deep learning model** trained on your own emotion data
- 🎵 **Music recommendations** based on emotion + language + singer
- 🌐 **Streamlit web app** interface with YouTube integration
- 📀 **Complete data collection and training pipeline included**

---

## 🫠 **Technologies Used**

- **Python 3** – Core programming language
- **OpenCV** – Webcam input and image processing
- **MediaPipe** – Real-time face and hand landmark detection
- **NumPy** – Data processing and storage
- **Keras (TensorFlow backend)** – Deep learning model
- **Streamlit** – Web app interface
- **streamlit-webrtc** – Live webcam streaming in Streamlit

---

## 🔧 **Modules Overview**

### 📅 `data_collection.py` – *Data Collection Module*

This script captures real-time landmark data from webcam for training:

- Captures **face and hand landmarks** using MediaPipe Holistic
- Normalizes coordinates relative to key points
- Records 100 frames of expression data per session
- Saves as `.npy` file named after the emotion (e.g., `happy.npy`)

### 🧠 `data_training.py` – *Model Training Module*

Trains a neural network model using the collected landmark data:

- Loads all `.npy` files in the directory
- Labels and one-hot encodes the data
- Shuffles and trains a deep neural network
- Saves the trained model as `model1.h5` and emotion labels as `labels.npy`

### 🔍 `inference.py` – *Real-Time Emotion Detection*

Detects emotion live using the webcam and trained model:

- Loads `model1.h5` and `labels.npy`
- Extracts and preprocesses facial and hand landmarks in real time
- Displays predicted emotion on video feed

### 🎶 `music.py` – *Streamlit Web App for Music Recommendation*

Interactive app that detects your emotion and recommends music:

- Built with **Streamlit** and **streamlit-webrtc** for live video
- Detects emotion and saves it in `emotion.npy`
- Accepts user inputs for **language** and **singer**
- Opens **YouTube** with relevant search like: `happy English song Arijit Singh`

---

## 🚧 **Setup Instructions**

### 1. **Install Dependencies**
```bash
pip install opencv-python mediapipe numpy keras streamlit streamlit-webrtc
```

### 2. **Run Data Collection**
```bash
python data_collection.py
```

### 3. **Train the Model**
```bash
python data_training.py
```

### 4. **Run Inference Script (Optional)**
```bash
python inference.py
```

### 5. **Launch Streamlit App**
```bash
streamlit run music.py
```

---

## 🌟 **Use Case**

Imagine sitting down after a long day, and your device starts playing music that understands your mood. Whether you're happy, sad, or excited—this app recommends songs that vibe with how you feel, just from your expressions.

---

## 📊 **Folder Structure**
```
Emotion-Based-Music-Player/
├── data_collection.py
├── data_training.py
├── inference.py
├── music.py
├── model1.h5
├── labels.npy
├── emotion.npy
├── *.npy (emotion datasets)
```

---
