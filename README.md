# Deep-learning-and-Computer-Vision

Deep learning is the subpart of machine learning that discovers and extracts the useful features from data using model. 
Deep learning can perform different tasks. 
The following are some tasks that can be performed by deep learning: -

  * Self driving car 
  *	Games
  *	Automatic colorization
  *	Cyber attack prediction, etc

Due to the above samples of success I understood that deep learning has many applications in the world. 
As machine leering, deep learning has models. Let’s see perceptron model

**Perceptron model** is simplest model of neuron that accept features in form of linear functions, 
combine them then change to the non-linear function. 
By using perceptron model, we get output inform of non-linear function

There are parts of perceptron model, which are: -
  *	Input 
  *	Summing point
  *	Activation function 
  *	Output 

 l learned about multilayer perceptron (MLP) which is the combine of more than one perceptron model.
 And below i mention typical training procedure for a neuron network which are as follow
 
  *	Define the neural network that has a learnable parameter
  *	Iterate over a dataset of input
  *	Process input through a network
  *	Compute a loss function (example MSEloss which compute mean-squared error between input and target
  *	Propagate gradient back into the networks parameters
  *	Update weights of the network 
  
  **NB:** the neural network packages contain various models and loss function that from the building block of deep neural network
And as you use neural network, you need to use various different update rule like 
  * SDG
  *	Nesterov – SDG
  *	Adam
  *	RMSProp

Activation function transforms the weighted sum of the inputs to the desired output. 
If the predicted value isn't desirable then loss is found by taking the actual value minus the predicted value. 
This loss (loss function) is the function of the internal parameters of the model.

Loss function can be: -
1.  Regressive loss function
    *	Absolute error
    *	Mean square error

2.  Classification loss function
    *	Cross entropy
    *	Binary class entropy
    *	Margin classifier
    *	Negative log likelihood
    
3.  Embedding loss function
    *	For measuring whether the two inputs are similar or dissimilar.
    
the quality of the deep neural network depends on the amount of data that we have. But in fact, 
the amount of data we have in real life is limited.

To overcome this, we have two option to create deep learning model 

  *	Transfer learning
  *	Data augmentation

With **transfer learning**, we can use the pre-trained model on one task and use it on our task (in case our task requires the same kind of input e.g Image) 
On this you can reduce the number of parameters that you'll need to train your new model as we know with more data we'll need more parameters.

With **data augmentation**, we aim to increase the size of the data that we have collected. we can apply the following techniques to increase the size of dataset.

  *	Cropping
  *	Flipping
  *	Translation 
  *	Rotation (with attention)


#                          Deep learning for Sequence Models
                          
Many real-world problems require processing a signal with sequence structure, example Machine translation,
Image captioning, Speech recognition, Music generation, object tracking, time series signal etc

With sequence models, 
  *	we need to deal with variable – length sequence and maintain sequence order
  *	keep track of long – term dependencies 
  *	and share parameters across the sequence

with MLP and CNN are limited with the need of sequence models as 

  MLP: 
  *	does not care about what happened at previous time step
  *	does not share feature learned across different position of a sequence
  *	Take fixed sized input and generates fixed sized output
  
  CNN:
  *	Does not handle arbitrary input/ output lengths
  *	Does not provide best way to handle long – term dependencies

Therefore, RNN family handle sequential data, as it uses the same idea like CNN by allow sharing of 
statistical features and generalize to unseen sequence during training. Also, each output is a function 
of the previous output with the same update rule applied

RNN maintain a recurrent state update at each time step t. And it offers a lot of flexibility

  *	Bidirectional RNN
  *	Deep RNN
  
There is different type of RNNs

  *	One to one (fixed size input to fixed sized output e.g. image classification)
  *	One to many (one input and sequence output e.g. image captioning)
  *	Many to one (sequence of input and one output e.g. sentimental analysis)
  *	Many to many (sequence input and sequence output e.g. machine translation)
  *	Many to many (synced sequence input and output e.g. video classification)

With RNN, there are two possible problem occurs during training the models when gradient propagated over 
many stages tends to emerged 

  *	**Vanishing gradient** when small gradient used leads to gradient to vanish/ shrink.
  *	**Exploding gradient** when large gradient used leads to gradient to explode.

Then, two common gated cells are used to overcome these problems are usually used and these are

*	Long short – term Memory (LSTM) where LSTM uses three specialized gates
    *	Forget gate 
    *	Input/update gate
    *	Output gate

*	Gated Recurrent Unit (GRU) a very simplified version of LSTM
    *	Merges forget and input gate into a single update gate thus it has reset gate and update gate

One of the advantages of GRU

    *	is that its simpler and can be used to build much bigger network

while LSTM 

    *	is more powerful.
