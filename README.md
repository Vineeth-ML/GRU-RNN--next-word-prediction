📖 Next Word Prediction with GRU RNN
A deep learning project that trains a Gated Recurrent Unit (GRU) recurrent neural network to predict the next word in a sequence, using Shakespeare's Hamlet as the training corpus.

🧠 Project Overview
This project demonstrates how sequence modeling with GRUs can learn the linguistic patterns of Shakespearean English. Given a phrase as input, the model predicts the most likely next word — for example:
Input:  "To be or not to be"
Output: "that"

Input:  "Mar. Horatio saies, 'tis but our"
Output: "fantasie"

🏗️ Model Architecture
The model is a stacked LSTM built with TensorFlow/Keras:
LayerOutput ShapeParametersEmbedding(None, 13, 100)481,800LSTM(None, 13, 150)150,600Dropout(0.2)(None, 13, 150)0LSTM(None, 100)100,400Dense(None, 4818)486,618
Total Parameters: 1,219,418 (~4.65 MB)

Loss: Categorical Crossentropy
Optimizer: Adam
Metric: Accuracy
Epochs: 100
Train/Test Split: 80/20

📂 Project Structure
.
├── GRU_RNN_.ipynb          # Main Jupyter notebook (training + evaluation)
├── hamlet.txt              # Raw text corpus (auto-downloaded via NLTK)
├── next_word_lstm.h5       # Saved trained model (generated after training)
├── tokenizer.pickle        # Saved tokenizer (generated after training)
├── requirements.txt        # Python dependencies
└── README.md


📦 Dependencies
See requirements.txt for full details. Key libraries:

tensorflow==2.21.0
pandas
numpy
scikit-learn
nltk
streamlit
scikeras
tensorboard
matplotlib


📊 Training Results
The model achieved approximately 78% training accuracy by epoch 100. Note that validation accuracy remains low (~5%) due to the high vocabulary diversity of Early Modern English — this is expected behavior for next-word prediction on a small, specialized corpus.

📝 Dataset
Shakespeare's Hamlet — sourced from NLTK's Gutenberg corpus, which includes a selection of public-domain texts. The raw text is auto-downloaded when you run the notebook.

Vocabulary size: 4,818 unique words
Corpus: Full text of Hamlet (lowercased)


🌐 Streamlit App
This project includes streamlit as a dependency for building an interactive next-word prediction web app. To launch it (once you have a trained model and tokenizer):
bashstreamlit run app.py

NLTK Gutenberg Corpus for the training data
TensorFlow / Keras for the deep learning framework
Streamlit for the app framework
