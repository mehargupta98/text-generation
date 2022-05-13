

# Text Generation using RNN and LSTM




Text Generation is a type of Language Modelling problem. Language Modelling is the core problem for a number of of natural language processing tasks such as speech to text, conversational system, and text summarisation. 

A trained language model learns the likelihood of occurrence of a word based on the previous sequence of words used in the text. Language models can be operated at character level, n-gram level, sentence level or even paragraph level.

**In this project, a language model is created for generating natural language text by implementing and training state-of-the-art **Recurrent Neural Network**.**

Unlike Feed-forward neural networks in which activation outputs are propagated only in one direction, the activation outputs from neurons propagate in both directions (from inputs to outputs and from outputs to inputs) in **Recurrent Neural Networks**. This creates loops in the neural network architecture which acts as a ‘memory state’ of the neurons. This state allows the neurons an ability to remember what have been learned so far.

The memory state in RNNs gives an advantage over traditional neural networks but a problem called **Vanishing Gradient** is associated with them. In this problem, while learning with a large number of layers, it becomes really hard for the network to learn and tune the parameters of the earlier layers. 

To address this problem, A new type of RNNs called **LSTMs** (Long Short Term Memory) Models have been developed. LSTMs have an additional state called ‘cell state’ through which the network makes adjustments in the information flow. The advantage of this state is that the model can remember or forget the leanings more selectively.

The project flow is briefly described in the following steps:

## 1. Loading the Dataset

 We have used Gutenberg eBook of The Adventures of Sherlock Holmes to train our model. (https://www.gutenberg.org/files/1661/1661-0.txt)

## 2. Data Preprocessing

- ### Generating Sequence of N-gram Tokens

Tokenization is a process of extracting tokens (terms / words) from a corpus. Python’s library Keras has inbuilt model for tokenization which is used to obtain the tokens and their index in the corpus. After this step, every text document in the dataset is converted into sequence of tokens.

- ### Padding the Sequences and obtain Variables : Predictors and Target

Now that we have generated a data-set which contains sequence of tokens, it is possible that different sequences have different lengths. Before starting training the model, we need to pad the sequences and make their lengths equal. We use pad_sequence function of Kears for this purpose. 

To input this data into a learning model, we created N-grams sequence as predictors and the next word of the N-gram as label.


## 3. Model Creation
A total of three layers are added in the model.
- Input Layer : Takes the sequence of words as input
- LSTM Layer : Computes the output using LSTM units. I have added 100 units in the layer, but this number can be fine tuned later.
- Dropout Layer : A regularisation layer which randomly turns-off the activations of some neurons in the LSTM layer. It helps in preventing over fitting. (Optional Layer)
- Output Layer : Computes the probability of the best possible next word as output

We ran this model for total 50 epochs but it can be experimented further.

## 4. Few Results:

Seed Text given as Input: *I could not help laughing at the ease with which he explained his process of deduction*

Output (100 words):

*I could not help laughing at the ease with which he explained his process of deduction* “**when i hear the gentle breathing of the companions which i have longed to the doings of hugh that lay forth the wild scream of the arabian i saw the blow the blow which was the stage lost which the amateur mendicant society who was thoroughly at home with a quiet and seven her until the time while i conduct of the house get his money for the coming of the day and explained that the second is to the main goodness to tell you the chain of a man with horror i remember the little that the gems had**




