# Datasets

Here we provide the graph datasets for GNN explanation.

More details of these datasets are described in [our paper](https://arxiv.org/abs/2012.15445).

We provide a unified data reader so different types of data can be easily loaded. The data reader supports all following datasets and the details can be found in `load_datasets.py` file.
  
## Synthetic datasets
The synthetic datasets are can be downloaded from [here](https://mailustceducn-my.sharepoint.com/:u:/g/personal/yhy12138_mail_ustc_edu_cn/ETK3CTHgFQVFhzIFB5piofQBv2Av-TsX_rnweymigve_hg?e=SyQjEX)

#### Node classification 
* BA-shapes 
* BA-Community
* Tree-Cycle 
* Tree-Grids

#### Graph classification 
* BA-2Motifs 
* BA-LRP 

## Text2Graph datasets

Here we provide graph data for text.
For each sentence, we take tokens as nodes and dependency relationships as edges to construct graph data.
In this way, we transfer SST2, SST5 and Twitter datasets into graph classification datasets.

The corresponding Graph-SST2, Graph-SST5 and Graph-Twitter can be downloaded
[here](https://drive.google.com/drive/folders/1aWKyqXTuiWgW7vFoxa8twCYscnyT_MzO?usp=sharing).

* Graph-SST2
* Graph-SST5
* Graph-Twitter 


### Molecule datasets

Molecule datasets are shown as below. 
We directly use the molecule datasets from the [Moleculenet](http://moleculenet.ai/datasets-1)
in Pytorch-Geometric. 
These datasets will be downloaded automatically. 
 
* BBBP
* Tox21
* BACE
* ClinTox


##Usage
Here we provide an example to use the data_loader interface.
```python
from load_datasets import get_dataset, get_dataloader
dataset = get_dataset(dataset_dir='./datasets', dataset_name=bbbp)
data_loader = get_dataloader(dataset, 
                             batch_size=32, 
                             random_split_flag=True, 
                             data_split_ratio=[0.8, 0.1, 0.1], 
                             seed=2)
```
  
## Citations
If you use our code and data, please cite our papers.

```
@misc{yuan2021explainability,
      title={On Explainability of Graph Neural Networks via Subgraph Explorations}, 
      author={Hao Yuan and Haiyang Yu and Jie Wang and Kang Li and Shuiwang Ji},
      year={2021},
      eprint={2102.05152},
      archivePrefix={arXiv},
      primaryClass={cs.LG}
}
```

```
@article{yuan2020explainability,
  title={Explainability in Graph Neural Networks: A Taxonomic Survey},
  author={Yuan, Hao and Yu, Haiyang and Gui, Shurui and Ji, Shuiwang},
  journal={arXiv preprint arXiv:2012.15445},
  year={2020}
}
```