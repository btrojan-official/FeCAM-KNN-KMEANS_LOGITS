# [FeNeC: Enhancing Continual Learning via Feature Clustering with Neighbor- or Logit-based Classification](https://arxiv.org/abs/2503.14301) [![Paper](https://img.shields.io/badge/ScienceDirect-Elsevier-blue)](https://www.sciencedirect.com/science/article/pii/S0950705126002224?dgcid=coauthor) [![Paper](https://img.shields.io/badge/arXiv-2503.14301-red)](https://arxiv.org/abs/2503.14301)

[![There should be a teaser...](teaser.png)](https://arxiv.org/abs/2503.14301)

## Abstract

The ability of deep learning models to learn continuously is essential for adapting to new data categories and evolving data distributions. In recent years, approaches leveraging frozen feature extractors
after an initial learning phase have been extensively studied. Many of these methods estimate per-class
covariance matrices and prototypes based on backbone-derived feature representations. Within this
paradigm, we introduce FeNeC (Feature Neighborhood Classifier) and FeNeC-Log, its variant based
on the log-likelihood function. Our approach generalizes the existing concept by incorporating data
clustering to capture greater intra-class variability. Utilizing the Mahalanobis distance, our models
classify samples either through a nearest neighbor approach or trainable logit values assigned to
consecutive classes. Our proposition may be reduced to the existing approaches in a special case
while extending them with the ability of more flexible adaptation to data. We demonstrate that two
FeNeC variants achieve competitive performance in scenarios where task identities are unknown and
establish state-of-the-art results on several benchmarks.

## Cite

```
@article{KSIAZEK2026115479,
        title = {FeNeC: Enhancing continual learning via feature clustering with neighbor- or logit-based classification},
        journal = {Knowledge-Based Systems},
        volume = {338},
        pages = {115479},
        year = {2026},
        issn = {0950-7051},
        doi = {https://doi.org/10.1016/j.knosys.2026.115479},
        url = {https://www.sciencedirect.com/science/article/pii/S0950705126002224},
        author = {Kamil Książek and Hubert Jastrzębski and Krzysztof Pniaczek and Bartosz Trojan and Michał Karp and Jacek Tabor},
        keywords = {Continual learning, Class-incremental learning, Nearest neighbors, Logit-based classifiers, Prototype-based classification, Feature space modeling, Exemplar-free continual learning, Catastrophic forgetting},
        abstract = {The ability of deep learning models to learn continuously is essential for adapting to new data categories and evolving data distributions. In recent years, approaches leveraging frozen feature extractors after an initial learning phase have been extensively studied. Many of these methods estimate per-class covariance matrices and prototypes based on backbone-derived feature representations. Within this paradigm, we introduce FeNeC (Feature Neighborhood Classifier) and FeNeC-Log, its variant based on the log-likelihood function. Our approach significantly extends the concept of per-class prototypes by constructing multiple, fine-grained sub-prototypes for each class, thereby enhancing the representation of class distributions. Utilizing the Mahalanobis distance, our models classify samples either through a nearest neighbor assignment to these sub-prototypes or trainable logit values assigned to consecutive classes. Our proposition can be seen as a generalization that reduces to existing single-prototype approaches in a special case, while extending them with the ability for more flexible adaptation to data. We demonstrate that our FeNeC variants establish state-of-the-art results across several benchmarks, proving particularly effective on CIFAR-100 and the complex ImageNet-Subset, where our method outperforms the strong FeCAM baseline by over 1% in average incremental accuracy and 1.5% in last task accuracy.}
}
```

## URLs

* [ScienceDirect](https://www.sciencedirect.com/science/article/pii/S0950705126002224?dgcid=coauthor)
* [arXiv](https://arxiv.org/abs/2503.14301)


## Alternative FeNeC implementation

There you can find the alternative version of FeNeC code:
https://github.com/gmum/FeNeC

## Python setup

First clone the repository using git and enter the FeNeC directory.
```bash
git clone https://github.com/btrojan-official/FeNeC.git
cd FeNeC
```
Then you need to setup Python enviroment

### Windows

```powershell
python3 -m venv .venv
.venv/Scripts/activate
pip install -r requirements.txt
```

### Linux

```bash
python3 -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
```

**Warning:** If you don't have cuda on your device, or you want to run code on other version of cuda than 12.4 you should manually change torch version in requirements.txt file!

If you have already prepared the virtual environment, don't forget to activate it with the commands below.

### Windows

```powershell
.venv/Scripts/activate
```

### Linux

```bash
source .venv/bin/activate
```

## Input Data Structure

Method **FeNeC.fit** that fits our model to training data takes two arguments:
- X_train - train data of shape (num_train_samples, num_features)
- y_train - train data labels of shape (num_train_samples)

Method **FeNeC.predict** that predicts the class of given test samples takes one argument:
- X_test - test data of shape (num_test_samples, num_features)

## Example Training Loop

After setting up you can run jupyter notebook with example training and evaluating loop: **train_and_eval.ipynb** file. It uses **config.py** from *configs* directory as configuration for model.

## Running experiments
To run experiments you should be in the repo directory use the following command:

```bash
python -m experiments.name_of_the_file_without_py --arg1 ... --arg2 ... --argn ...
```

## FeNeC implementation

The FeNeC model code is in the **model.py** file. With some other helper functions implemented in the files inside of the *utils* directory.

## Contact

Contact with the authors of this code:
- bartosztrojanofficial@gmail.com
- contact@michalkarp.pl

Or other authors of this paper:
- kamil.ksiazek@uj.edu.pl
- h.jastrzebski@student.uj.edu.pl
- krzysiek.pniaczek@outlook.com
- jacek.tabor@uj.edu.pl
