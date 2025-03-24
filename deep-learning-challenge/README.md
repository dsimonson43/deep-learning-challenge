# deep-learning-challenge

##Deep-Learning-Challenge-Report##

#Purpose of Analysis 

#The purpose of this analysis was to develop a binary classification model, utilizing deep learning neural networks that attempt to predict whether the selected organizations applying for funding via the Alphabet Soup foundation will be successful. The goal of this project was to...
1) Effectively Preprocess the data
2) Build a performing model that exceeds an accuracy threshold of 75%

#Results

***Data Preprocessing***

-Target variable: IS_SUCCESSFUL -- indicates whether an organization received funding (1) or not (0)

-Feature Variables

-One-hot encoded values (APPLICATION_TYPE, CLASSIFICATION, INCOME_AMT, ASK_AMT_BINNED)

-Variables that were removed:

1) EIN (Holds no value for predictions)
2) NAME (Not useful for modeling; identifying info)
3) STATUS (irrelevant, redundant)
4) SPECIAL_CONSIDERATIONS (Irrelevant, redundant)

-Compiling, Training, Evaluating Model

I used input layers that match the numbers of features after encoding. Additionally, there are 4 hidden layers:
Layer 1) 256 neurons, ReLU activation, BatchNormalization, 40% dropout
Layer 2) 128 neurons, ReLU activation, BatchNormalization, 30% dropout
Layer 3) 64 neurons, ReLU activation, BatchNormalization 20% dropout
Layer 4) 32 neurons, ReLU activation, BatchNormalizationm 10% dropout
Output layer: 1 neuron, sigmoid activation

***Activation Functions***

-ReLU
-Sigmoid

***Model Optimizer, Training***
Optimizer: Adam with a learning rate of .0005
Loss function: binary crossentropy
Epochs: 150 (EarlyStopping <= 15 epochs of no improvement)
Batch size: 32
Callbacks: EarlyStopping with restore_best_weights=True

***Model Performance***

I did not achieve the goal of higher than 75% accuracy, as my model performed at 72.3% accuracy. The loss value was measured at .5588

What steps did I take to improve the model's performance? I added additional dense layers, utilized BatchNormalization, introduced Dropout layers to reduced model overfitting, slowed the learning rate and increased training epochs, implemented EarlyStopping, and verified the dataset balance to ensure there was no class weighting required. 
The deep learning model achieved a respectable 73.34% accuracy, falling just short of the 75% target. Through careful data preprocessing, architecture tuning, and regularization techniques, the model showed substantial improvement from an initial 66% accuracy.

***Recommendation***
While the deep learning model performed decent, a different approach could potentially outperform it. If attempted again, I would try a gradient boosting model such as XGBoost. 

These are powerful tree-based ensemble models that often perform better on tabular data with categorical variables.

Why this recommendation?

Neural networks excel with image, text, and complex non-linear data.

Tabular data like this often favors ensemble methods due to their ability to handle categorical values, missing data, and feature interactions more naturally.
