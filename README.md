# 📘 Text Generation Using LSTM

## 📌 Overview
This project implements a **word-level text generation model** using a  
**Long Short-Term Memory (LSTM)** neural network.

The model is trained on the **Shakespeare dataset (Project Gutenberg)** and
generates new text based on a given seed input.

The objective of this assignment is to demonstrate practical understanding of:
- Natural Language Processing (NLP)
- Sequence modeling using LSTM
- Generative text modeling
- Sampling strategies for text generation

---

## 📂 Dataset
- **Source:** Project Gutenberg – Complete Works of William Shakespeare
- **Format:** Plain text (`.txt`)
- **Preprocessing Steps:**
  - Converted text to lowercase
  - Removed Gutenberg license and metadata
  - Tokenized text at the word level

---

## ⚙️ Technologies Used
- Python
- TensorFlow / Keras
- NumPy
- Jupyter Notebook

---

## 🧠 Model Architecture
- Embedding Layer
- LSTM Layer
- Dense Output Layer with Softmax activation

**Training Configuration:**
- Loss Function: `sparse_categorical_crossentropy`
- Optimizer: Adam

Using sparse categorical cross-entropy avoids one-hot encoding and significantly
reduces memory usage for large vocabularies.

---

## 🔄 Training Process
- Text is converted into n-gram sequences
- Each sequence predicts the next word
- Sequences are padded to a fixed length
- Model is trained for a limited number of epochs

**Note:**  
Due to hardware limitations, the dataset size was capped during training while
preserving overall language patterns.

---

## ✍️ Text Generation
After training, the model generates text iteratively from a seed phrase.

To reduce repetition and improve diversity, **temperature-based sampling** is used:
- **Temperature = 0.5:** Safer, more repetitive text
- **Temperature = 0.8:** Balanced and coherent output
- **Temperature = 1.2:** More creative but less grammatical text

---

## ▶️ How to Run
1. Install dependencies:
   ```bash
   pip install tensorflow numpy
Place the dataset file in:
data/dataset.txt

Open and run the Jupyter Notebook:
text_generation_lstm.ipynb

📈 Results

The trained model successfully generates Shakespeare-style text and demonstrates:

Learned sentence structure

Context awareness

Controlled creativity using temperature sampling

🚀 Future Improvements

Add Dropout layers for better regularization

Train for more epochs on higher-end hardware

Implement character-level text generation

Save and reload trained models for reuse
