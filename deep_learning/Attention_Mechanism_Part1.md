#### Introduction
Attention mechanism has become one of the most popular research fields  nowadays due to the great success of BERT and GPT-3. In this article, we will introduce and analyse the attention mechanism in a intuitive way. Before we dive into the detail, let me list out some crucial concepts and questions about attention mechanism in deep learning:

- Concept No.1: In brief, attention is nothing but **trainable weights combined with some explicilty defined calculation**.

- Concept No.2: The purpose of applying attention in NLP task is to solving the issue called "long-term dependency" of the "seq2seq" model.

- Concept No.3: There are a variety of ways of defining attention mechanism for deep learning models.

- Concept No.4: The well-known "Transformer" model is a deep neural network which entirely based on "self-attention" mechanism.

- Question No.1: What is "seq2seq" model?

- Question No.2: What is "long-term dependency" issue?

- Question No.3: If attention is just trainable weights of the neural networks, then what is the difference between attention's weights and the conventional weights of the neural networks(e.g. the weights of a MLP)?

- Question No.4: What is the relationship between "attention" and "self-attention"?

Now, let's inspect the details of attention mechanism while keeping the concepts and questions above in our mind.

#### It all starts with the Seq2Seq model
Sequence to sequence ("Seq2Seq") models take a sequence data as input, then output a processed sequence data. It is widely used in NLP tasks like machine translation and speech recognition. The length of the input and output sequence could be different, e.g. chinese phrase "机器学习" translated into english would be "machine learning".
In brief, attention is nothing but trainable weights plus explicilty defined calculation between some tensors. It model the importance of each part of the inputs. Take the most popular "Transformer" model as an example: In Natural Language Processing (**NLP**), the inputs are the embedded tensor of each word of a sentence. In Computer Vision (**CV**) the input are the flattened tensor of each "patch" which cropped from the whole image.

[![attention_demo](https://images.algorithmic.cn/images/Attention_Mechanism_Part1/attention_demo.gif "attention_demo")](https://images.algorithmic.cn/images/Attention_Mechanism_Part1/attention_demo.gif "attention_demo")

However, in deep learning we could regard the deep neural networks as trainable weights as well. Then what's the difference between the "conventional trainable weights" and attention? As far as I'm concerned, the difference is pretty subtle, attention just correlates the output tensor (referred to as "Query", "Key", "Value" in the paper ["Attention is All You Need"](https://arxiv.org/abs/1706.03762 "Attention is All You Need")) by applying some specific differentiable calculations on the output tensors. But those changes make the deep learning models work surprisingly well and beat the conventional RNN and CNN in many fields. I'll go through these concepts in detail in the upcoming posts, here we just depict those concepts roughly for better intuitively understanding.


#### Why Using Attention
The prime motivation for applying attention mechanism is that it improves the training&inference speed of the neural network drastically (especially compared with RNN). It is stated in the paper "Attention is All you Need" that **"The Transformer allows significantly parallelization"** because of the introducing of attention mechanism.


