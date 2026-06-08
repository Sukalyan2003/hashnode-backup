---
title: "Intro to deep learning MIT"

---

Working notes for everything you learn while going through the course.

## Week 1

This deals with the Basics of the Deep learning landscape, giving some overview and then jumping straight into Perceptrons, Backpropagation and more. I have already covered these topics in a [previous post](https://sukalyanroy.hashnode.dev/understanding-neural-networks) which you can refer to.

After that, in the next lecture they cover topics like Recurrent Neural networks.

The fundamental idea of the Recurrence can be summarized as follows:

Instead of data only moving from one layer to the next, make sure that there is data moving amongst nodes of the same layer, and also between later layers to previous layers. This can model a sense of progression of time.

But this is also susceptible to exploding or vanishing values. If the data gets too large or too small at any point at all.

To fix this there are several methods like dropout, normalization, etc. But the lectures essentially focus on the ideas rather than the implementation.

Following which it builds up to the transformer architecture, which i have also covered in a [previous post](https://sukalyanroy.hashnode.dev/what-even-are-llms) at a basic level, let me know if you're interested in a detail post on the architecture itself.

All the preamble done, now it's time to get hands on the code labs.

### Code lab 1 - Music Generation

The intro notebook had some basic syntax, but more importantly, it made me think about the Autograd feature of Pytorch.  
  
I was under the impression that it is just another term for Vanilla Backpropagation, but technically it's slightly different.

Pytorch's Autograd is the most famous example perhaps of Generalized reverse order auto differentiation, which is just a fancy way of saying that it helps differentiate complex nested functions using the chain rule, which is essential for backpropagation.

How autograd automates it, is by using a Directed Acyclic Graph(DAG) to keep track of every single operation as it goes through the forward pass that we decide based on model architecture. And then figures out how the backpropagation chain rule should proceed.

Without this, we would have to manually map out exactly how the gradients flow back, which is something that I covered in the first post linked at the top.

### The Main Model

Here, most of the things were pretty well explained, and almost every time i stumbled here, it was because I lacked a clear idea of how the shape of different layers change.

Once you figure that out, you can just refer to the documentation of Pytorch and easily write a model of any architecture.

The main idea here is less about music and more about text prediction. We get sheet music in a simple format, and we treat it as a text corpus and predict the next symbols.  
The actual conversion to and from this text to actual audio files is done via a library provided by the Instructors.