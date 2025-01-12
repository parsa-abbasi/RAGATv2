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
| RotateE | 0.338 | <u>177</u> | 0.241 | 0.375 | 0.533 |
| R-GCN | 0.248 | - | - | - | 0.417 |
| KBGAT | 0.157 | 270 | - | - | 0.331 |
| InteractE | 0.354 | <b>172</b> | 0.263 | - | 0.535 |
| COMPGCN | 0.355 | 197 | 0.264 | 0.390 | 0.535 |
| RAGAT | <u>0.365</u> | 199 | <b>0.273</b> | <u>0.401</u> | <u>0.547</u> |
| RAGATv2 | <b>0.366</b> | 192 | <b>0.273</b> | <b>0.403</b> | <b>0.551</b> |

### WN18RR
| Model | MRR | MR | Hit@1 | Hit@3 | Hit@10 |
| :---: | :---: | :---: | :---: | :---: | :---: |
| TransE | 0.226 | 3384 | - | - | 0.501 |
| DistMult | 0.430 | 5110 | 0.390 | 0.440 | 0.490 |
| ComplEx | 0.440 | 5261 | 0.410 | 0.460 | 0.510 |
| ConvE | 0.430 | 4187 | 0.400 | 0.440 | 0.520 |
| RotateE | 0.476 | 3340 | 0.428 | 0.492 | <u>0.571</u> |
| R-GCN | - | - | - | 0.137 | - |
| KBGAT | 0.412 | <b>1921</b> | - | - | 0.554 |
| InteractE | 0.463 | 5202 | 0.430 | - | 0.528 |
| COMPGCN | 0.479 | 3533 | <u>0.443</u> | 0.494 | 0.546 |
| RAGAT | <b>0.489</b> | 2390 | <b>0.452</b> | <b>0.503</b> | 0.562 |
| RAGATv2 | <u>0.486</u> | <u>1986</u> | 0.440 | <b>0.503</b> | <b>0.577</b> |

## How to reproduce the results?
* Make sure you are using the same seed (`41504`) for all the experiments.
* Train the model for `1000` epochs for FB15k-237 and `2400` epochs for WN18RR.
  * **Personal note:** As I used the Tesla T4 GPU, provided by Kaggle, I could not train the model for `1000` or `2400` epochs. I trained the model for `200` and `150` epochs for FB15k-237 and WN18RR, respectively, and saved the checkpoints. Then, I restarted the kernel and loaded the checkpoints to continue the training process. I repeated this process until I reached the number of epochs mentioned above.

## Acknowledgement
The implementation is built upon [COMPGCN](https://github.com/malllabiisc/CompGCN) and [RAGAT](https://github.com/liuxiyang641/RAGAT).
