# Fine-tuning BERT for text-classification

Problem statement
The aim is to develop a machine learning algorithm to predict whether a tweet is about a real disaster or not.

Aproach
Transfer learning technique is used to perform the text classification problem. We load pretrained BERT model and finetune the weights.

Advantages of fine-tuning
Time - Pretrained BERT model weights already encode a lot of information. As a result, it takes much less time to finetune the model

Data - As the pretrained model is trained on large text, the model performs well even with small datasets.

We don't go into the details of BERT architecture. Here is an overview about how BERT is pretrained, and how it can be used for classification.

BERT (Bidirectional Encoder Representations from Transformers)¶
Language modeling is a common method of pretraining on unlabeled text (self supervised learning). Most of the language models learned by iteratively predicting next word in a sequence auto regressively across enormous data sets of text like wikepedia. This can be left to right, right to left or bi-directional.

There are two strategies of applying pretrained language representations to downstream tasks:

Feature based approach
Fine tuning approach
The feauture based approach, such as ELMo uses task specific architectures that include the pretrained representations as additional features.

The fine tuning approach, such as OpenAI GPT, introduces minimal task specific parameters, and is trained on the downstream task by fine tuning all the pretrained parameters.

BERT model can be used for both the approaches. BERT reformulates the language modeling pretrained task of iteratively predicting the next word in sequence to instead incorporate bidirectional context and predict mask of intermediate tokens of the sequence and predict the mask token. BERT presented a new self supervised learning task for pretaining transformers inorder to fine tune them for different tasks. They major difference between BERT and prior methods of pretraining transformer models is using the bidirectional context of language modeling. Most of the models either move left to right or right to left to predict next word in sequence, where BERT tries to learn intermediate tokens (by MASK), making the name Bidirectional Encoder.

BERT uses Masked language model and also use "Next sentence prediction" task.

BERT uses 3 embeddings to compute the input representations. They are token embeddings, segment embeddings and position embeddings.

BERT Transformer will preserve the length of the (dimention of the) input. The final output will take this vector and pass these to seperate tasks (classification, in this case).

BERT for Classification
BERT consists of stacked encoder layers. Just like the input of encoder of the transformer model, BERT model takes the sequence of numeric representation of the tokens as input. For classification tasks, we must prepend the special [CLS] token to the beginning of every sentence.

Encoder block of transformer outputs a vector with same length as of input. First position of the vector, corresponding to the [CLS] token, can now be used as the input for a classifier.

