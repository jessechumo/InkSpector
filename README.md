# 🖋️ Inkspector: Signature Forgery Detection with Deep Learning

Inkspector is a deep learning project that detects forged handwritten signatures using a Siamese Convolutional Neural Network (Siamese CNN). By comparing a test signature against a known genuine sample, the model learns to distinguish subtle differences between authentic and forged signatures.

## 📌 Project Overview

Forgery detection is a critical problem in banking, legal, and academic sectors. Traditional visual inspection methods are subjective and error-prone. Inkspector leverages deep learning to automate and improve the accuracy of signature verification.

Instead of treating signature classification as a binary task (real vs forged), Inkspector uses a pairwise comparison approach: it determines whether two signatures come from the same person.

## 🧠 Model Architecture

- **Siamese Neural Network** using shared CNN branches
- Each branch processes an input signature image and learns deep feature representations
- The model uses **L1 distance** to compare the features of a test signature and a known genuine sample
- Final prediction: **same (genuine)** or **different (forged)**
![image](https://github.com/user-attachments/assets/41a50222-23cd-401d-8ea3-bdf201a6c669)


## 🧾 Dataset

The dataset used is [Handwritten Signatures | Genuine and Forged](https://www.kaggle.com/datasets/divyanshrai/handwritten-signatures) from Kaggle.

- 150 genuine + 150 forged signatures (300 total)
- Format: Grayscale `.png` images

**Dataset Structure:**
- `genuine/`: 5 samples each from 30 individuals
- `forged/`: 5 forged samples for the same 30 individuals

**File Naming Convention:** `NFI-XXXYYZZZ`
- `XXX`: ID of the person who performed the signature
- `YY`: Sample number
- `ZZZ`: ID of the person the signature claims to represent

**Examples:**
- `NFI-00602023`: Person 006 forged a signature of person 023 → **forged**
- `NFI-02103021`: Person 021 signed their own signature → **genuine**

## 🧪 Performance
![image](https://github.com/user-attachments/assets/bfed7cfc-fc20-420b-8399-b0ad179e0423)


- **Training Accuracy:** 99.46%
- **Validation Accuracy:** 97.14%
- Custom **confusion heatmaps** and model visualization included 
<p float="left">
  <img src="https://github.com/user-attachments/assets/e78fc04a-f8d3-4541-ad36-12934e229c74" width="45%" />
  <img src="https://github.com/user-attachments/assets/99e069de-c534-404c-8044-3081c7004024" width="45%" />
</p>


  - The model in action below.
![image](https://github.com/user-attachments/assets/cf9b3265-46e8-4163-9298-f566009b193d)


## 📂 Project Structure

```
Inkspector/
├── sample_Signature/
│   ├── genuine/
│   └── forged/
├── dasv.ipynb           # Main notebook
├── Signature Forgery Detection.pptx
├── requirements.txt       
└── README.md
```

## 🚀 How to Run

1. **Clone this repo**
```bash
git clone https://github.com/your-username/inkspector.git
cd inkspector
```

2. **Create and activate a virtual environment**
```bash
python -m venv venv
source venv/bin/activate   # For Linux/macOS
venv\Scripts\activate      # For Windows
```

3. **Install dependencies**
```bash
pip install -r requirements.txt
```

4. **Run the notebook**
```bash
jupyter notebook dasv.ipynb
```
## ✅ Features

- Siamese architecture for pairwise signature verification
- Heatmap visualizations to evaluate model behavior
- Plot of network architecture using Matplotlib
- Clean preprocessing with padding, normalization, and resizing
- Compatible across Linux (CPU) and Windows (GPU)

## 🔮 Future Work

- Expand dataset with real-world samples
- Add data augmentation for robustness
- Experiment with deeper or hybrid models
- Deploy as a web app for real-time signature verification

## 🧑‍💻 Credits

- Dataset: [Divyansh Rai on Kaggle](https://www.kaggle.com/datasets/divyanshrai/handwritten-signatures)
