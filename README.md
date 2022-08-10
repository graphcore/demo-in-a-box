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

### Trying out IPUs from Gradient

| Content | Run on Paperspace |
|---------|-------------------|
|PyTorch Tutorials Repo|[![Gradient](https://assets.paperspace.io/img/gradient-badge.svg)](https://console.paperspace.com/github/graphcore/tutorials?machine=Free-IPU-POD16&container=graphcore%2Fpytorch-jupyter%3A2.6.0-ubuntu-20.04-20220804)|
|Tensorflow2 Tutorials Repo|[![Gradient](https://assets.paperspace.io/img/gradient-badge.svg)](https://console.paperspace.com/github/graphcore/tutorials?machine=Free-IPU-POD16&container=graphcore%2Ftensorflow-jupyter%3A2-amd-2.6.0-ubuntu-20.04-20220804)|
|Tensorflow1 Tutorials Repo|[![Gradient](https://assets.paperspace.io/img/gradient-badge.svg)](https://console.paperspace.com/github/graphcore/tutorials?machine=Free-IPU-POD16&container=graphcore%2Ftensorflow-jupyter%3A1-amd-2.6.0-ubuntu-18.04-20220809)|
|PyTorch Examples Repo|[![Gradient](https://assets.paperspace.io/img/gradient-badge.svg)](https://console.paperspace.com/github/graphcore/examples?machine=Free-IPU-POD16&container=graphcore%2Fpytorch-jupyter%3A2.6.0-ubuntu-20.04-20220804)|
|Tensorflow2 Examples Repo|[![Gradient](https://assets.paperspace.io/img/gradient-badge.svg)](https://console.paperspace.com/github/graphcore/examples?machine=Free-IPU-POD16&container=graphcore%2Ftensorflow-jupyter%3A2-amd-2.6.0-ubuntu-20.04-20220804)|
|Tensorflow1 Examples Repo|[![Gradient](https://assets.paperspace.io/img/gradient-badge.svg)](https://console.paperspace.com/github/graphcore/examples?machine=Free-IPU-POD16&container=graphcore%2Ftensorflow-jupyter%3A1-amd-2.6.0-ubuntu-18.04-20220809)|
|HuggingFace Optimum Repo|[![Gradient](https://assets.paperspace.io/img/gradient-badge.svg)](https://console.paperspace.com/github/huggingface/optimum-graphcore?machine=Free-IPU-POD16&container=graphcore%2Fpytorch-jupyter%3A2.6.0-ubuntu-20.04-20220804)|
|BERT-Large (HF / Examples Repo)|[![Gradient](https://assets.paperspace.io/img/gradient-badge.svg)](https://console.paperspace.com/github/gradient-ai/Graphcore-PyTorch?machine=Free-IPU-POD16&container=graphcore%2Fpytorch-jupyter%3A2.6.0-ubuntu-20.04-20220804&file=%2Fget-started%2FFine-tuning-BERT.ipynb)|
|BERT-Large (HF Optimum )|[![Gradient](https://assets.paperspace.io/img/gradient-badge.svg)](https://console.paperspace.com/github/gradient-ai/Graphcore-HuggingFace?machine=Free-IPU-POD16&container=graphcore%2Fpytorch-jupyter%3A2.6.0-ubuntu-20.04-20220804&file=%2Fnotebook-tutorials%2Fintroduction_to_optimum_graphcore.ipynb)|
|ViT (HF Optimum)|[![Gradient](https://assets.paperspace.io/img/gradient-badge.svg)](https://console.paperspace.com/github/gradient-ai/Graphcore-HuggingFace?machine=Free-IPU-POD16&container=graphcore%2Fpytorch-jupyter%3A2.6.0-ubuntu-20.04-20220804&file=%2Fget-started%2Fwalkthrough.ipynb)|
|RoBERTa (HF Optimum)|[![Gradient](https://assets.paperspace.io/img/gradient-badge.svg)](https://console.paperspace.com/github/gradient-ai/Graphcore-HuggingFace?machine=Free-IPU-POD16&container=graphcore%2Fpytorch-jupyter%3A2.6.0-ubuntu-20.04-20220804&file=%2Fnotebook-tutorials%2Ftext_classification.ipynb)|
|Cluster-GCN Tensorflow2 |[![Gradient](https://assets.paperspace.io/img/gradient-badge.svg)](https://console.paperspace.com/github/gradient-ai/Graphcore-Tensorflow2?machine=Free-IPU-POD16&container=graphcore%2Ftensorflow-jupyter%3A2-amd-2.6.0-ubuntu-20.04-20220804&file=%2Fget-started%2Frun_cluster_gcn_notebook.ipynb)|
|SchNet (PyG)|[![Gradient](https://assets.paperspace.io/img/gradient-badge.svg)](https://console.paperspace.com/github/gradient-ai/Graphcore-PyTorch?machine=Free-IPU-POD16&container=graphcore%2Fpytorch-jupyter%3A2.6.0-ubuntu-20.04-20220804&file=%2Fget-started%2FPyG-SchNetGNN.ipynb)|
|TGN (Tensorflow1)|[![Gradient](https://assets.paperspace.io/img/gradient-badge.svg)](https://console.paperspace.com/github/gradient-ai/Graphcore-Tensorflow1?machine=Free-IPU-POD16&container=graphcore%2Ftensorflow-jupyter%3A1-amd-2.6.0-ubuntu-18.04-20220809&file=%2Fget-started%2FTrainingTGN.ipynb)|