# Demo in a Box: BERT-Large Fine-tuning on IPU

This repository is a starter kit for presenting a live 20 minute demonstration
on how to fine-tuning a pre-trained BERT model with PyTorch and Hugging Face 
transformers on the IPU. The full code and notebook is available in the 
[BERT Fine-tuning tutorials repo](https://github.com/graphcore/tutorials/tree/master/tutorials/pytorch/tut_finetuning_bert). 

In order to streamline your experience, we have created some simple scripts 
which aims to minimise the demo setup time and even make the demo accessible 
to users with minimal experience of using IPUs.
## What is covered in this demo

A Jupyter notebook demo walking through how to fine-tune a pre-trained BERT 
model with PyTorch on a Graphcore IPU-POD16 system using the SQuADv1 dataset and running an inference question / answering task.
This demo notebook can be found in [Tutorials: Finetuning BERT](https://github.com/graphcore/tutorials/tree/master/tutorials/pytorch/tut_finetuning_bert).

Demo outline:

* Step-by-step guide for pre-processing the SQuAD dataset for training 
  deep learning models using the Transformers library from Hugging Face
* How to run and optimize the pre-trained BERT model on IPU by leveraging 
  pipelining and data parallelism techniques with PopTorch
* A simple inference demo using the fine-tuned model to define tasks and 
  answer questions in real time with state-of-the-art performance
## How to run this demo

### Trying out IPUs from Jupyter

The simplest ways to use the IPUs for your first application and to complete our
tutorials is using Jupyter. To help you get setup quickly we have put together
scripts and Docker files in the [jupyter-docker](jupyter-docker/README.md) folder.
