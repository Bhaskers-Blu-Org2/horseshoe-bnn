# Interpretable Outcome Prediction with Sparse Bayesian Neural Networks in Intensive Care

This repository contains all code for the paper **Interpretable Outcome Prediction with Sparse
Bayesian Neural Networks in Intensive Care** which can be found [here](https://arxiv.org/pdf/1905.02599.pdf). 

**Abstract:**
Clinical decision making is challenging because of pathological complexity, as well as large amounts of heterogeneous data generated by various medical instruments. In recent years, machine learning tools have been developed to aid clinical decision making. Especially models for outcome prediction in intensive care units (ICUs) could help, for example, with decisions about resource allocation. However, flexible tools such as deep neural networks are rarely deployed in healthcare systems due to a lack of interpretability. In this work, we propose a novel interpretable Bayesian neural network (BNN) architecture, which offers both the flexibility of artificial neural networks and interpretability in terms of feature selection. In particular, we employ a sparsity inducing prior distribution in a tied manner to learn which features are important for performing outcome prediction. In addition, our model is fully probabilistic. Thus, the model provides probabilistic outcome prediction results, as well as information about the importance of different input features (i.e. clinical measurements). We evaluate our approach on the task of mortality prediction using two cohorts from real-world intensive care units. Collaborating with healthcare experts, we found that our approach can provide novel insights into the importance of different clinical measurements, in addition to the predicted outcome results. This suggests that our model can support medical experts in their decision making.

# Table of Contents
1. [Installation](#installation)
2. [Citation](#citation)
3. [Datasets](#datasets)
4. [Getting started](#getting-started)
5. [Structure of repository](#repository-structure)
6. [License](#license)
7. [Contributing](#contributing)

## Installation

The code runs in Python 3.7 and Pytorch 1.1. To install the package please first clone the repo. After that, navigate to the project and run the following command in your command line
```bash
pip install -e .
```

Other requirements can be installed using the requirements file located in the repo:
```bash
pip install -r requirements.txt
```

## Citation
If you use this code in your research, please cite the following publication:

### Bibtex
@article{popkes2019,
  title={Interpretable Outcome Prediction with Sparse Bayesian Neural Networks in Intensive Care},
  author={Popkes, Anna-Lena and Overweg, Hiske and Ercole, Ari and Li, Yingzhen and Hern{\'a}ndez-Lobato, Jos{\'e} Miguel and Zaykov, Yordan and Zhang, Cheng},
  journal={arXiv preprint arXiv:1905.02599},
  year={2019}
}

### MLA
Popkes, Anna-Lena, et al. "Interpretable Outcome Prediction with Sparse Bayesian Neural Networks in Intensive Care." arXiv preprint arXiv:1905.02599 (2019).

### APA
Popkes, A. L., Overweg, H., Ercole, A., Li, Y., Hernández-Lobato, J. M., Zaykov, Y., & Zhang, C. (2019). Interpretable Outcome Prediction with Sparse Bayesian Neural Networks in Intensive Care. arXiv preprint arXiv:1905.02599.

## Datasets 

1. [MIMIC-III](https://mimic.physionet.org/)
- Instructions on how to download the dataset can be found [here](https://mimic.physionet.org/gettingstarted/access/)
- Details on the dataset, including preprocessing and features can be found in [our paper](https://arxiv.org/pdf/1905.02599.pdf)

2. [Center TBI dataset](https://www.center-tbi.eu/data)
- This dataset is not publically available
- Details on the dataset, including preprocessing and features can be found in [our paper](https://arxiv.org/pdf/1905.02599.pdf)

3. [Boston Housing Dataset](https://scikit-learn.org/stable/modules/generated/sklearn.datasets.load_boston.html)
- To demonstrate the functioning of our networks and evaluator we use a publically available dataset, available within sckikit-learn
- The [example script](https://github.com/Microsoft/horseshoe-bnn/blob/master/horseshoe_bnn/evaluation/evaluate_all_models.py
) for running the evaluator uses this dataset

## Getting started

A script which trains and evaluates all models on the [Boston Housing Dataset](https://scikit-learn.org/stable/modules/generated/sklearn.datasets.load_boston.html) can be found [here](https://github.com/Microsoft/horseshoe-bnn/blob/master/horseshoe_bnn/evaluation/evaluate_all_models.py). The script contains an example of how to train the models using the evaluator.

The code for the individual models is located [here](https://github.com/Microsoft/horseshoe-bnn/blob/master/horseshoe_bnn/models.py
).

## Repository Structure

```
├── LICENSE
├── README.md          <- The top-level README for developers using this project.
│
├── requirements.txt   <- The requirements file for reproducing the analysis environment
│
├── test               <- All pytest test code
│
├── mimic_preprocessing <- Scripts to preprocess the MIMIC-III dataset
│
├── horseshoe_bnn       <- All source code
│    │
│    ├── __init__.py    <- Makes horseshoe_bnn a Python module
│    │
│    ├── data_handling        <- Scripts to handle data
│    │   │                
│    │   ├── dataset.py                <- Custom Dataset class
│    │   └── dataset_to_dataloaders.py <- Function to convert Dataset instance to Pytorch dataloader
│    │
│    │
│    ├── evaluation     <- Scripts to evaluate models
│    │   │                 
│    │   ├── evaluator.py           <- Evaluator
│    │   └── evaluate_all_models.py <- Example script how to run evaluation
│    │
│    ├── metrics.py              <- Metric classes
│    ├── models.py               <- All model classes
│    ├── distributions.py        <- Distribution classes
│    ├── network_layers.py       <- BNN network layer classes
│    ├── aggregation_result.py   <- Aggregation result class
│    └── parameters.py           <- Parameter classes
│
└── 
```

## License

This repository is licensed under the Microsoft Research license.

## Contributing

This project welcomes contributions and suggestions.  Most contributions require you to agree to a
Contributor License Agreement (CLA) declaring that you have the right to, and actually do, grant us
the rights to use your contribution. For details, visit https://cla.microsoft.com.

When you submit a pull request, a CLA-bot will automatically determine whether you need to provide
a CLA and decorate the PR appropriately (e.g., label, comment). Simply follow the instructions
provided by the bot. You will only need to do this once across all repos using our CLA.

This project has adopted the [Microsoft Open Source Code of Conduct](https://opensource.microsoft.com/codeofconduct/).
For more information see the [Code of Conduct FAQ](https://opensource.microsoft.com/codeofconduct/faq/) or
contact [opencode@microsoft.com](mailto:opencode@microsoft.com) with any additional questions or comments.
