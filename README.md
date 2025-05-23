# CA-FATA
Implementation of CA-FATA

## Description

In this paper we propose CA-FATA, context-aware features attribution through argumentation. Our framework harnesses the power of argumentation by treating each feature as an argument that can either support, attack or neutralize a prediction. Additionally, CA-FATA formulates feature attribution as an argumentation procedure, and each computation has explicit semantics, which makes it inherently interpretable. CA-FATA also easily integrates side information, such as users’ contexts, resulting in more accurate predictions.

## A toy example
![A graphical representation of an argumentation procedure in a recommendation scenario. Each node represents an argument, at represents a feature of an item, the central node represents an argument "This item can be recommended to the target user". The value on the arc denotes the strength and polarity of the argument, "+" denotes supports, "-" denotes attacks, and "0" denotes neutralizes. ](https://github.com/JinfengZh/ca-fata/blob/master/figures/toy.png)

A graphical representation of an argumentation procedure in a recommendation scenario. Each node represents an argument, at represents a feature of an item, the central node represents an argument "This item can be recommended to the target user". The value on the arc denotes the strength and polarity of the argument, "+" denotes supports, "-" denotes attacks, and "0" denotes neutralizes.

## Major steps

![The major steps CA-FATA](https://github.com/JinfengZh/ca-fata/blob/master/figures/fata_steps.png)
## Structure of files
* data file contains the data used to generate results, to generate the training and the test set, please refer to the data_processing_frappe.ipynb for the Frappe dataset and data_processing_yelp.ipynb for the Yelp dataset.
* Figure files contains the toy example, major steps of CA-FATA and the cluster of the Frappe dataset. To generate the cluster, please refer to graph_frappe.ipynb for the Frappe dataset and graph_yelp.ipynb for the Yelp dataset.

## Executing codes

* name controls the selection of dataset, n_epochs defines the number of epochs, dim is the dimension of embedding, l2_weight is the regularization rate, lr is the learning rate, context_or = True means that users' contexts are considered, average_or = True means that the importance of features is considered.

* On the Frappe dataset

```
python3 main.py --name 'Frappe' --e_epochs 100 --dim 256 --batch_size 256 --l2_weight 5e-5 --lr 5e-3 --context_or True --average_or True
```
* On the Yelp dataset
```
python3 main.py --name 'Yelp' --e_epochs 100 --dim 16 --batch_size 4096 --l2_weight 1e-3 --lr 5e-2 --context_or True --average_or True
```

## Explanation scenarios of CA-FATA
At least three applications for generating explanations can be envisaged: 
### Toy templates
### Interactive explanations
### Contrsative explanations
