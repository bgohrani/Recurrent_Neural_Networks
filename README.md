# Recurrent Neural Networks

## Hey There!

This repo consists of some of the code I've created while learning and implementing, Recurrent Neural Networks. These are a class of dynamic artificial neural networks where nodes
are connected to one another along a temporal sequence. This characteristic makes them very effective when it comes to dealing with variable length sequences, and consequently, text data. The outputs of one node of the network form a part of the input of the next, and thus RNNs maintain a memory of the previous data they've seen. The data in a RNN flows through the network and can be used to generate an output at any point in the sequence. RNNs are thus primarily used in _Natural Language Processing_, besides other applications. We'll first look at a simple task with a RNN and then move on to a more challening, _Machine Transliteration_ problem.

**RNNs** Notebook Outline:
- Loading a names-to-language file and encoding the data for training, studying the distribution of the data.
- Writing down a simple vanilla RNN for classification of the names.
- Building helper functions to process the data to form batches, send it through the RNN and calculate accuracy.
- Building two training functions, one to train a single batch of data and the other to call it to train multiple batches.
- Implementing the LSTM and GRU cells instead of the regular RNN to improve accuracy by selective read and write.
- Plotting a confusion matrix to visualize the performance of the model.
- Training process replicated with GPU hardware support.
- Implementing batching in RNNs to speed up the training process.
- Batching using LSTM and GRU cells in the network.


## Sequence-to-Sequence classification using Encoder-Decoder models in PyTorch

This repository contains a project, which implments a **Neural Machine Transliteration** task by using RNNs to form Encoder-Decoder Models. In Deep Learning, it is common to be dealing with sequences which are of unequal length, thus requiring two separate RNNs. The first RNN is known as the Encoder Model and takes in an input sequence and forms an encoded hidden state which serves as an output of the model. The actual outputs of each of the cells in the RNN is commonly not of much significance. The hidden and cell states of the encoder RNN are passed as the initial hidden and cell states of the second RNN, known as the Decoder. It is here that the output sequence is generated. This RNN has a different set of weights and uses the output of the previous cell as the input to the next. The Decoder RNN givens out a sequence which serves as the output of the model and is used for computation of loss which then forms gradients that flow all the way back to the encoder. Since one sequence is taken as an input and a sequence is also returned as an output, these are commonly known as _Sequence-to-Sequence models_. In this project, we will be implementing a transliteration problem, conversion of english words to hindi.

**Project: Encoder_Decoder_Machine_Transliteration** Notebook Outline:
- Import the training and test data xml files into the workspace.
- Writing down functions for cleaning strings to spearate out words and remove special characters.
- Writing down a class that neatly processes our data for us and returns equiavalent lists of cleaned hindi and english words along with batches if necessary.
- Writing functions to encode the data (Not the enocder we have seen above, similar to one-hot like encoding)
- Building the Encoder and Decoder architecture, as well as the sequence-to-sequence class to call them as required.
- Initializing weights, setting up the training and evaluation function and training the model.

Note: This work is greatly inspired by _Ben Trevett's_ tutorials on implementing a few sequence-to-sequence (seq2seq) models with PyTorch and TorchText. You can check out the repository [here](https://github.com/bentrevett/pytorch-seq2seq). The training and testing data I've used has been attached in the repository here.


**Project_Encoder_Decoder_Batched** Notebook:
Often when we work with Neural Networks, we can make use of their full potential and the enormous power of vectorization to speed up the training process. We also know that this technique is very popular when working with FeedForward Neural Networks. The same can also be done with RNNs. However, we face a challenge while doing so. The whole concept of RNNs is needed since we deal with variable length data. How do we then, send it in the form of batches? Some preprocessing is needed while doing so. The approach that we have used here is that we send sequences which are of the same length as a single batch. The lengths may vary across batches but remain constant within a batch. Using this method, I have recreated my project by implementing batching for the transliteration task. The entire notebook remains the same, except for the training function, where the idea is implemented.
