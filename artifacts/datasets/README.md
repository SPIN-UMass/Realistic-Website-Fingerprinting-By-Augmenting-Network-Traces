# Dataset Overview

We release our collected Tor traces for the Drift dataset as well as the AWF dataset created by processing the traces collected by Rimmer et al. [1] which we obtained by contacting the authors.


Please find the full detail of the categorization and processing of the datasets in our paper. Please cite the following paper as we use their dataset.

```
[1]: Vera Rimmer, Davy Preuveneers, Marc Juarez, Tom Van Goethem, and WouterJoosen. 2018.  
Automated Website Fingerprinting through Deep Learning. In Proceedings of the 25nd Network 
and Distributed System Security Symposium (NDSS 2018). Internet Society.
```

The following is the layout of this directory:
```
.
├── drift
│   ├── Drift90.npz
│   └── Drift5000.npz
└── README.md
```

Each `npz` archive file can be opened to read the `numpy` arrays contained in it. For example:
```
import numpy as np

data = np.load('<filename>.npz')
array_names = data.files
for array_name in lst:
    print(data[array_name])
```

# Dataset Descriptions

The traces for the Drift dataset and the AWF dataset can be found in the and [`awf`](./awf/) directories, respectively. The download link to some of the larger files 

<br />


### Drift dataset
The `npz` files in the [`drift`](./drift/) directory represent the *open world* and *closed world* datasets. Each include `numpy` arrays for the sequences of Tor cells (`X`), their labels (`y`) for both superior and inferior traces, as well as the mapping of the websites to labels.

* [Drift90](./drift/Drift90.npz): Fine-tuning Drift dataset with 90 websites.
* [Drift5000](./drift/Drift5000.npz): 5000 open-world traces of the Drift dataset. 

<br />

### AWF dataset

1.  Traditional WF scenario

    For traditional WF scenario, we use AWF1 and AWF2 datasets. You can download these datasets using following links:
    * [AWF1](https://drive.google.com/file/d/1ZQqc_pZBSJuwqbniCol-WR14jf--tLPZ/view?usp=sharing): 100 website with 2500 traces each.
    * [AWF2](https://drive.google.com/file/d/1hT__6CZ_QTaD6K04Gn46PoA3P44LHvpb/view?usp=sharing): 100 websites with 2500 traces each. The AWF1 and AWF2 websites are distinct. 

    Note that we only use 500 samples from AWF2 to perform the pre-training for NetCLR.

2. Realistic WF scenario
    
    Open world:
    * [`AWF-OW`](https://drive.google.com/file/d/1mrhI51RsrYmNNqsYsI05iFwtYtpuPfRC/view?usp=share_link): The traces of the open-world AWF dataset. The `npz` file includes the sequences of Tor cells, the labels, as well as the corresponding network condition metric (NCM) values.
    * [`AWF-OW-URLs`](https://drive.google.com/file/d/17GHbxmPSwSyiqk9GG3iYzP1V1BOcNrNh/view?usp=sharing): The URLs for the open-world websites. The `npy` file contains the list of websites whose indices are used as labels in the dataset. 

    <br />


    Closed world: 

    The two pre-training datasets, AWF-PT<sub>sup</sub> and AWF-PT<sub>inf</sub>, were used for the pre-training phase. Each include the traces, their labels, the mapping of websites to labels, and the list of corresponding NCM values. The AWF-Attack dataset includes both the superior and the inferior Tor traces, their labels, and the mapping of websites to labels. You can download the datasets using the following links:

    * [`AWF-Attack`](https://drive.google.com/file/d/1ZpatzDlAnAos0kTk7mLvztApaDhbSzZQ/view?usp=sharing): Superior and inferior traces of the fine-tuning AWF dataset.
    * [AWF-PT<sub>sup</sub>](https://drive.google.com/file/d/1cuISvRsgzFta5KR82SoL6eM4X8Zg7SOh/view?usp=sharing): Superior traces for pre-training.
    * [AWF-PT<sub>inf</sub>](https://drive.google.com/file/d/1ApKj61C2DfU4qlvlCvm7O5EVG8eS_HbF/view?usp=sharing): Inferior traces for pre-training. We use this dataset to investigate the effect of pre-training on inferior traces showin in Table 3 of the paper.