README

Word Embedding classification task:
1. File: 1_LogisticRegression.ipynb
		--> Used to evaluate different preprocessing techniques
2. File: 2_LogisticRegressionCrossEvaluation.ipynb
		--> Used to tune hyperparameters of and cross-validate Logistic Regression model
3. File: 3_NeuralNetwork.ipynb
		--> Used to build and cross-validate Neural Network

Needed Files in working directory:
- project_training.json
- project_validation.json
- glove.6B.300d.txt (https://nlp.stanford.edu/data/glove.6B.zip)
- NLP_project_unlabelled_slim.txt
- metrics_new.xlsx --> empty Excel file needed to be able to export results

Workin environment:
Anaconda environment in combination with any IDE supporting Jupyter (e.g. DataSpell).
See the environment_GPU.yml file for used packages.
If in possesion of a computer with a relatively new graphics card, GPU acceleration can be used for training the NN.