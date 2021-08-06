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
