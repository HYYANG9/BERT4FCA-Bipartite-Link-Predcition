# BERT4FCA
This is the codebase for the paper: [BERT4FCA: A Method for Bipartite Link Prediction using Formal Concept Analysis and BERT](https://arxiv.org/abs/2402.08236)
## Overview
Bipartete link prediction is the task of predicting the absence or presence of unobserved links in a **bipartite network**. There are two types of bipartite link prediction. The first type predicts the missing links between nodes from different node sets, such as recommender system. The second tyoe predicts the missing links between nodes from the same node sets, such as predicting the newly formulated co-authorship in an author-paper bipartete network.  

We propose **BERT4FCA**, a method for both bipartete link prediction tasks in bipartite networks using formal concept analysis(FCA) and BERT. We use FCA to extract all maximal bi-cliques and their order relations. Then we use BERT to learn the information extracted by FCA and use the trained BERT to make link prediction. 


## Architecture
![Workflow of BERT4FCA](https://github.com/HYYANG9/BERT4FCA/files/14277024/Figure_4.pdf)


## Files Description
### Dataset
This file contains all three datasets used in the paper.
BMS-POS is a product purchased transactions network provided by KDD Cup 2000.  
ICFCA is an author-paper network.  
Paper-keyword is an original dataset generated from the DBLP dump.    

### Object-Object Prediction
This file contains the codebase of bipartite link prediciton between nodes from the same node sets on each dataset.   
In BMS-POS dataset, we predict two products will be likely to be bought by the same customer.   
In ICFCA dataset, we predict future co-authorships or seek potential co-authors from an author-paper network at a certain time point.   
In Parper-keyword dataset, we predict potentially related keywords, which may give inspiration for new research.   

### Object-Attribute Prediction
This file contains the codebase of bipartite link prediction between nodes form different node sets on each dataset. For each dataset, we pre-train a BERT model on objects and another model on attributes, then fine-tune on the two pre-trained BERT. We predict the potentially missing links given the known network. 

### Citation
Please cite our paper as:
```
Peng S, Yang H, Yamamoto A (2024) BERT4FCA: A method for bipartite link prediction using formal concept analysis and BERT. PLoS ONE 19(6): e0304858. https://doi.org/10.1371/journal.pone.0304858
```
