> [E] What’s the motivation for RNN?

The motivation for RNN is to model sequential relationships in data. RNNs receive
inputs sequentially and have a hidden state that allows to memorize information from previous time steps that can be used for prediction at the current time step. This inductive bias makes RNNs suitable for modeling sequential relationships in data. Other models, such as a multilayer perceptron, cannot model the relation between different samples out of the box.

> [E] What’s the motivation for LSTM?

The motivation for LSTM is to model long-term dependencies in sequential data. It addresses one traditional problem that RNNs have, which is the so-called "vanishing gradient" problem. This problem makes the gradients on the back-propagation phase to be increasingly small as the data sequence increases. This decrease in the gradients magnitude makes the network's parameters update very small too, making overall training very unstable. LSTM's architecture solves this by introducing the concept of a "memory cell", which can store information over long periods of time. In addition, LSTMs architecture also allows selectively removing or adding new information to this "memory cell" as it receives new data.

> [M] How would you do dropouts in an RNN?

> [E] What’s density estimation? Why do we say a language model is a density estimator?

> [M] Language models are often referred to as unsupervised learning, but some say its mechanism isn’t that different from supervised learning. What are your thoughts?
Word embeddings.

Some language models are considered self-supervised learning models, which is a subfield of unsupervised learning. For self-supervised learning, we have a weak supervision signal that is obtained from the data, without using any explicit labels. For example, in a language learning model, the model has to predict the next word in a sentence given the previous words. This task gives the model some feedback which allows it to learn a good representation of the input data. So, both supervised and self-supervised learning models have a supervision signal, hence the comparison.

> [M] Why do we need word embeddings?

We need word embeddings to encode semantically meaningful information about a word in a numerical way, so it can be introduced to a machine learning model. Semantic information describes the meaning of a word. Therefore, words that have similar meanings will be closer to each other in the embedding space than those that have
completely different meanings.

> [M] What’s the difference between count-based and prediction-based word embeddings?

> [H] Most word embedding algorithms are based on the assumption that words that appear in similar contexts have similar meanings. What are some of the problems with context-based word embeddings?


> Given 5 documents:
 - D1: The duck loves to eat the worm
 - D2: The worm doesn’t like the early bird
 - D3: The bird loves to get up early to get the worm
 - D4: The bird gets the worm from the early duck
 - D5: The duck and the birds are so different from each other but one thing they have in common is that they both get the worm

> [M] Given a query Q: “The early bird gets the worm”, find the two top-ranked documents according to the TF/IDF rank using the cosine similarity measure and the term set {bird, duck, worm, early, get, love}. Are the top-ranked documents relevant to the query?

> [M] Assume that document D5 goes on to tell more about the duck and the bird and mentions “bird” three times, instead of just once. What happens to the rank of D5? Is this change in the ranking of D5 a desirable property of TF/IDF? Why?

> [E] Your client wants you to train a language model on their dataset but their dataset is very small with only about 10,000 tokens. Would you use an n-gram or a neural language model?

> [E] For n-gram language models, does increasing the context length (n) improve the model’s performance? Why or why not?

> [M] What problems might we encounter when using softmax as the last layer for word-level language models? How do we fix it?

> [E] What's the Levenshtein distance of the two words “doctor” and “bottle”?

> [M] BLEU is a popular metric for machine translation. What are the pros and cons of BLEU?

> [H] On the same test set, LM model A has a character-level entropy of 2 while LM model A has a word-level entropy of 6. Which model would you choose to deploy?

> [M] Imagine you have to train a NER model on the text corpus A. Would you make A case-sensitive or case-insensitive?

> [M] Why does removing stop words sometimes hurt a sentiment analysis model?

Some stop words may convey useful information about the sentiment of a sentence.
For example, if we wanted to train a sentiment analysis model for movie review, we may have a sentence like this: "Inception is THE movie". If we remove "THE", the emphasis is removed, and key information about the sentiment about that movie is lost.

> [M] Many models use relative position embedding instead of absolute position embedding. Why is that?

> [H] Some NLP models use the same weights for both the embedding layer and the layer just before softmax. What’s the purpose of this?