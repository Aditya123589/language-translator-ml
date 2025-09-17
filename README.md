# 🗣️ English → French Language Translator (Seq2Seq LSTM)

A character-level **English-to-French translator** built with **TensorFlow/Keras** (sequence-to-sequence LSTM) and a simple **Tkinter GUI** for interactive translation.  
This project was inspired by DataFlair tutorials.

---

## ✨ Features

- ✅ **Sequence-to-Sequence LSTM** architecture with Encoder–Decoder  
- ✅ **Character-level tokenization** using CountVectorizer  
- ✅ **Trainable model** with customizable dataset (`eng-french.txt`)  
- ✅ **Tkinter GUI** for real-time English to French translation  
- ✅ **Pickle-based storage** for vocabulary and parameters  

---

## 🗂 Project Structure

```
.
├── eng-french.txt        # Dataset: English ↔ French sentence pairs
├── training_data.pkl     # Saved vocabulary and parameters (created after training)
├── s2s/                  # Saved model directory (created after training)
├── model_plot.png        # Visual architecture of the model
├── translator.py         # Main code (training + GUI)
└── README.md             # This file
```

---

## ⚙️ Requirements

Install the dependencies:

```bash
pip install tensorflow scikit-learn numpy pickle5
```

For the GUI:

```bash
pip install tk
```

---

## 🚀 How to Run

### 1️⃣ Train the Model  
Make sure you have the dataset `eng-french.txt` (tab-separated English and French sentence pairs).  
Run:

```bash
python translator.py
```

The code will:
- Load data from `eng-french.txt`
- Create encoder/decoder inputs
- Train the LSTM model
- Save the model as `s2s` and parameters as `training_data.pkl`

### 2️⃣ Launch the Translator GUI  
Once training is done, the Tkinter GUI starts automatically.  
Type your English text in the input box and click **Send** to see the French translation.

---

## 🧠 Model Architecture

- **Encoder**: LSTM (256 hidden units)  
- **Decoder**: LSTM (256 hidden units, returning sequences)  
- **Dense layer**: Softmax over French character vocabulary  

The model uses teacher forcing during training and autoregressive decoding during inference.

---

## 📊 Dataset

- Use the provided `eng-french.txt` or your own dataset.  
- Format: Each line must have an English and French sentence separated by a **tab**.  
Example:

```
Go.	Vas-y.
Run!	Cours !
Stop!	Arrêtez !
```

---

## 🖥️ GUI Preview

- **Top area**: Welcome message  
- **Main area**: Conversation-style output showing “English” input and “Decoded” translation  
- **Bottom area**: Input entry + Send button  

---

## 🛠️ Customization

- Change `epochs` in `model.fit()` to train longer or shorter.  
- Adjust `LSTM(256)` to a larger number for better capacity.  
- Replace dataset with other language pairs.

---

## 📝 License

This project is released under the **MIT License**. Feel free to fork, modify, and share.

---

  
