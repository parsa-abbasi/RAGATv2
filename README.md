# RAGATv2

This repository contains the code for the thesis project "Improving the Overparameterization and Static Attention Problems in Relational Graph Attention Networks" by [Parsa Abbasi](https://parsa-abbasi.github.io/)

## Abstract

Link prediction in multi-relational graphs is a fundamental task involving the prediction of missing links based on available triples. Graph Neural Networks (GNNs) have emerged as effective methods for capturing complex graph structures. However, existing GNN-based models for multi-relational graphs often suffer from overparameterization and static attention limitations, which hinder their capacity to effectively capture intricate relational patterns. In this thesis, an enhanced model known as RAGATv2 is introduced. This model is built upon the structure of the Relation Aware Graph Attention Network (RAGAT). A pivotal enhancement lies in the attention mechanism. Unlike its predecessor, RAGATv2 adopts a dynamic attention mechanism inspired by the innovative concept introduced in GATv2. This enhancement improves information aggregation by considering both node embeddings and relational context, resulting in more accurate predictions. Furthermore, the issue of overparameterization is addressed through a judicious design of the model architecture, leading to a reduction in the number of trainable parameters compared to the original RAGAT. The evaluation conducted on the FB15k-237 and WN18RR datasets demonstrates the superiority of RAGATv2, achieving Hit@10 scores of 0.551 and 0.577, respectively. RAGATv2 outperforms other methods in 4 out of 5 metrics on FB15k-237 and 2 out of 5 metrics on WN18RR, showcasing a substantial improvement over RAGAT and the baselines. 

## Dependencies
- python 3.10.12
- torch 2.0.0
- ordered-set 4.1.0

## Datasets
- FB15k-237
- WN18RR

## Results
### FB15k-237
| Model | MRR | MR | Hit@1 | Hit@3 | Hit@10 |
| :---: | :---: | :---: | :---: | :---: | :---: |
| TransE | 0.294 | 357 | - | - | 0.465 |
| DistMult | 0.241 | 254 | 0.155 | 0.263 | 0.419 |
| ComplEx | 0.247 | 339 | 0.158 | 0.275 | 0.428 |
| ConvE | 0.325 | 244 | 0.237 | 0.365 | 0.501 |
| RotateE | 0.338 | 177 | 0.241 | 0.375 | 0.533 |
| R-GCN | 0.248 | - | - | - | 0.417 |
| KBGAT | 0.157 | 270 | - | - | 0.331 |
| InteractE | 0.354 | 172 | 0.263 | - | 0.535 |
| COMPGCN | 0.355 | 197 | 0.264 | 0.390 | 0.535 |
| RAGAT | 0.365 | 199 | 0.273 | 0.401 | 0.547 |
| RAGATv2 | 0.366 | 192 | 0.273 | 0.403 | 0.551 |

## Acknowledgement
The implementation is built upon [COMPGCN](https://github.com/malllabiisc/CompGCN) and [RAGAT](https://github.com/liuxiyang641/RAGAT).
