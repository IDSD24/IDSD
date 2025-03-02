# Aggregately Diversified Sequential Recommendation

This project is a PyTorch implementation of SAPID: Diversified and Accurate Recommendations for a Series of Users


## Prerequisites
- Python 3.8+
- [PyTorch](https://pytorch.org/)
- [NumPy](https://numpy.org/)
- [Scipy](https://scipy.org)
- [Click](https://click.palletsprojects.com/en/7.x/)
- [tqdm](https://tqdm.github.io/)


## Datasets
We provide 4 datasets in this project: Gowalla, Amazon-electronics, Amazon-home, and Ml-1m.
We include the preprocessed datasets in the repository: `data/{data_name}`
Use git lfs with following scripts after clone this repository to download datsets.
```
curl -s https://packagecloud.io/install/repositories/github/git-lfs/script.deb.sh | sudo bash
sudo apt install git-lfs
git lfs pull
```


## Base model
We provide 2 most widely used sequential recommendation models: SASRec and GRU4Rec.
We adopt the implementation of [pmixer](https://github.com/pmixer/SASRec.pytorch) for SASRec,
and the implementation of [PatrickSVM](https://github.com/PatrickSVM/Session-Based-Recommender-Models/) for GRU4Rec.
The implemented models are given in `model.py` and pretrained parameters are given in `model/`.

## Usage

### Training phase
You can run the training code by `python train.py` with arguments `--base`, `--data`, `--epochs`, and `--alpha`.
The role of each argument is as follows:

* `--data`: choose a dataset
* `--base`: choose a base model
* `--epochs`: choose a number of epochs
* `--alpha`: choose a debiasing hyperparameter $\alpha$

### Recommendation phase
You can run the evaluation code by `python eval.py` with arguments `--base`, `--data`, `--epochs`, `--alpha`, and `--candn`.
The role of each argument is as follows:

* `--data`: choose a dataset
* `--base`: choose a base model
* `--epochs`: choose a number of epochs
* `--alpha`: choose a debiasing hyperparameter $\alpha$
* `--candn`: choose a size $c$ of candidate pool
