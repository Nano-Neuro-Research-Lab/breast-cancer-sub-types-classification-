# AFExNet: An Adversarial Autoencoder for Differentiating Breast Cancer Sub-types and Extracting Biologically Relevant Genes [[Paper]](https://www.mdpi.com/2072-6694/15/9/2569)
[![License: CC BY 4.0](https://img.shields.io/badge/License-CC%20BY%204.0-lightgrey.svg)](https://creativecommons.org/licenses/by/4.0/)
[![contribution](https://img.shields.io/badge/contributions-welcome-brightgreen.svg?style=flat)](https://github.com/raktimmondol/breast-cancer-sub-types-classification/pulls)
![python version](https://img.shields.io/badge/python-2.7%20%7C%203.5%20-green.svg)
![keras version](https://img.shields.io/badge/keras-2.0.6-brightgreen.svg)
![tensorflow version](https://img.shields.io/badge/tensorflow-1.13.1-orange.svg)
![imblearn version](https://img.shields.io/badge/imbalanced--learn-0.4.3-blue.svg)

In this project, we demonstrate how adversarial auto-encoder (AAE) model can be used to extract the features from high dimensional genetic (omics) data. We evaluated the performance of the model through twelve diﬀerent supervised classiﬁers to verify the usefulness of the new features in breast cancer subtypes prediction.

+ For biological insight please follow this link: https://github.com/NeuroSyd/latent-space-discovery

![project_logo_transparent](https://user-images.githubusercontent.com/28592095/56498063-8039da00-6543-11e9-8b4a-a551bad3ed0f.png)



## Getting Started

The following instructions will get you a copy of the project up and running on your local machine for development and testing purposes. See the instruction below:

### Prerequisites

The following libraries are required to reproduce this project:

1) Keras 2.0.6 is recommended but works up to 2.1.2 

2) Keras-adverserial (0.0.3)
Download Link: https://github.com/bstriner/keras-adversarial
install by using "python setup.py install" 

3) Tensorflow (1.13.1)

4) Scikit-Learn (0.20.3)

5) Numpy (1.16.3)

6) Imbalanced-Learn (0.4.3)

Supports both Python 2.7.0 and Python 3.5.6

Hyperparameters of classifiers are optimized using TPOT https://github.com/EpistasisLab/tpot

### Directory Layout
```bash
├── results
│   ├── figures
│   │   ├── Here figures will be stored
│   ├── result.tsv
├── data
│   ├── data will be stored here
├── feature_extraction
│   ├── AAE
│   │    ├── 1
│   │    ├── 2
│   │    ├── 3
│   │    ├── 4
│   │    ├── 5          # five folder for five fold cross validation
│   │    ├── fine_tuned
│   │    │    ├── 1
│   │    │    ├── 2
│   │    │    ├── 3
│   │    │    ├── 4
│   │    │    ├── 5
│   ├──deepAE
│   ├──denoisingAE
│   ├──shallowAE
│   ├──VAE
├── README.md
├── notes.txt
└── .gitignore
```
Make sure to keep the directory as following for other feature extraction methods:
```
.
├── ...
├── feature_extraction                   
│   ├── denoisingAE       # same for deepAE, shallowAE and VAE
│   │    ├── 1
│   │    ├── 2
│   │    ├── 3
│   │    ├── 4
│   │    ├── 5            
└── ...
````
### Usage

Run the following to train and fine tune the autoencoder

```
main.py
```

And run the following when model already fine tuned

```
without_fine_tuning.py
```

### Benchmarking Code

```
import timeit
start_time = timeit.default_timer()
import psutil
import os
....................
....................
....................
....... code .......
....................
....................
....................
start_time = timeit.default_timer()


###### COMPUTATION TIME ########
print('Wall Clock Time')
print ((end_time - start_time), 'Sec')
time=(end_time - start_time)
minutes = time // 60
time %= 60
seconds = time
print(minutes, 'Minutes', seconds,'Seconds')

########  CPU USAGE #######
print('CPU Usage') 
print(psutil.cpu_percent(), '%')
print('THE END')
```
To know the MEMORY USAGE please follow the instruction below:

Install memory profiler library: https://pypi.org/project/memory-profiler/ then run the following command.

```
mprof run main.py
```
Finally see the memory usage by running:
```
mprof plot
```

## Proposed Architecture

![AFExNET](https://user-images.githubusercontent.com/28592095/115665054-821e1a00-a364-11eb-9774-6f72ef5bd589.png)


## Datasets

* [cBioPortal](https://www.cbioportal.org/) - Cancer Genomics Datasets
* [Breast Invasive Carcinoma (TCGA, Cell 2015)](http://www.cbioportal.org/study?id=brca_tcga_pub2015) - Clinical information is used to label various molecular subtypes

``` Breast Invasive Carcinoma (BRCA) ```

| Molecular Subtypes | Number of Patients | Label |
| ------------------ | ------------------ | ------------ |
| Luminal A | 304 | 0 |
| Luminal B | 121 | 1 |
| Basal & Triple Negetive | 137 | 2 |
| Her 2 Positive | 43 | 3 |

| Total Number of Samples (Patients) | Total Number of Features (Genes) |
| :------------------: | :------------------: |
| 605 | 20439 |

* [Details about Molecular Subtypes of Breast Cancer](https://www.breastcancer.org/symptoms/types/molecular-subtypes)

## Contribution

If you want to contribute to this project and make it better, your help is very welcome. When contributing to this repository please make a clean pull request.


## Acknowledgments

* The proposed architecture is inspired by https://github.com/bstriner/keras-adversarial

## Tech Stack
![tech_stack_banner](https://user-images.githubusercontent.com/28592095/115676246-358d0b80-a371-11eb-9482-0752d5a27d3f.png)

## Cite Us: 
![alt text](https://github.com/adam-p/markdown-here/raw/master/src/common/images/icon48.png "Logo Title Text 1")
If you find this code useful in your research, please consider citing:
```
@ARTICLE{9378938,
  author={R. K. {Mondol} and N. D. {Truong} and M. {Reza} and S. {Ippolito} and E. {Ebrahimie} and O. {Kavehei}},
  journal={IEEE/ACM Transactions on Computational Biology and Bioinformatics}, 
  title={AFExNet: An Adversarial Autoencoder for Differentiating Breast Cancer Sub-types and Extracting Biologically Relevant Genes}, 
  year={2021},
  volume={},
  number={},
  pages={1-1},
  doi={10.1109/TCBB.2021.3066086}}
```
