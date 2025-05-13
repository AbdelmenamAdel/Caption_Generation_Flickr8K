# 📸 Image Captioning using CNN + NLP + LSTM | Flickr8k Dataset

This project implements an **Image Caption Generator** that uses deep learning techniques combining **Convolutional Neural Networks (CNN)** and **Recurrent Neural Networks (RNN)** — specifically, **LSTM** — to generate human-like captions for images.

> 🔗 [Access the Dataset & Notebook on Google Drive](https://drive.google.com/drive/folders/1SRlq-X3TZMQUDWAzBQJGpGmixIVmP2rb?usp=drive_link)

---

## 📚 Dataset: Flickr8k

- **8,000 images**, each with **5 captions**
- Descriptive, real-world image data
- Source: [Flickr8k on Kaggle](https://www.kaggle.com/datasets/adityajn105/flickr8k)

---

## 🚀 Workflow Overview

1. **Feature Extraction:**
   - Use a **pre-trained VGG16 CNN** (without top layer)
   - Resize images to `224x224`
   - Extract and save features in a dictionary

2. **Text Preprocessing:**
   - Clean and normalize captions
   - Add `<start>` and `<end>` tokens
   - Use **Keras Tokenizer**, pad sequences

3. **Model Architecture:**
   - **CNN Path**: VGG16 → Dense → Dropout
   - **Caption Path**: Embedding → LSTM
   - Merge both → Dense → Word prediction

4. **Training:**
   - Loss: `categorical_crossentropy`
   - Optimizer: `adam`
   - Evaluate using BLEU score

5. **Caption Generation:**
   - Predict next word step-by-step until `<end>`

---

## 🛠 Libraries & Tools

- Python
- TensorFlow / Keras
- NumPy, Pandas, Matplotlib
- PIL, TQDM
- VGG16 (pre-trained on ImageNet)

---

## 🔧 How to Run on Google Colab

1. Mount Google Drive:

   ```python
   from google.colab import drive
   drive.mount('/content/drive')

2. Upload your kaggle.json to authenticate with Kaggle:

!pip install kaggle
from google.colab import files
files.upload()  # upload kaggle.json

3. Set Kaggle directory and download dataset:

- !mkdir ~/.kaggle
- !cp kaggle.json ~/.kaggle/
- !chmod 600 ~/.kaggle/kaggle.json
- !kaggle datasets download -d adityajn105/flickr8k -p /content/
- !unzip -q /content/flickr8k.zip -d /content/flickr8k

4. Run the notebook cells and follow instructions

📸 Example Output
Input Image	Generated Caption
🧒 Child playing in sand	a child is playing on the beach

🧠 Model Highlights

- CNN used for vision
- LSTM used for language generation
- Caption generation word-by-word
- Handles overfitting using:
- Dropout
- Early stopping
- Data split for validation

🙋 Author
Abdel Moneim

Junior Flutter & AI Developer
🔗 [LinkedIn](https://www.linkedin.com/in/abdelmenam-adel-175b35265/) | 📧 [Email](abdelmoneim.adel5@gmail.com)

📂 Try it now!
📥 Download Dataset & Notebook