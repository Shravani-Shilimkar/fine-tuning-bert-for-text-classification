# fine-tuning-bert-for-text-classification

Problem statement
The aim is to develop a machine learning algorithm to predict whether a tweet is about a real disaster or not.

Aproach
Transfer learning technique is used to perform the text classification problem. We load pretrained BERT model and finetune the weights.

Advantages of fine-tuning
Time - Pretrained BERT model weights already encode a lot of information. As a result, it takes much less time to finetune the model

Data - As the pretrained model is trained on large text, the model performs well even with small datasets.

We don't go into the details of BERT architecture. Here is an overview about how BERT is pretrained, and how it can be used for classification.
