# NetCLR

This directory includes the implementation of NetCLR. 

## Reproduce Results

[`pre-training.ipynb`](./pre-training.ipynb): This notebook implements the pre-training phase of NetCLR using AWF-PT<sub>sup</sub> dataset. 

[`fine-tuning-cw.ipynb`](./fine-tuning-cw.ipynb): This notebook implements the fine-tuning and attack pahses of NetCLR in the closed world scenario. The notebook also includes the results for 5 labeled traces ($N=5$) and AWF dataset. 

[`fine-tuning-ow.ipynb`](./fine-tuning-ow.ipynb): This notebook implements the fine-tuning and attack phases of NetCLR in the open world scenario. The notebook outputs include the precision and recall for 5 labeled traces ($N = 5$) and the $Drift$ dataset. 

You can reproduce the results by changing $N$ for different number of labeled samples and $DATASET$ for the $Drift$ dataset. 
Note that we sample $N$ number of labeled traces randomly and therefore, the results may not be exactly same as the ones in the paper. 