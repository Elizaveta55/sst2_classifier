# SST-2 Classifier
This is a research of an appropriate classifier for SST-2 dataset from GLUE

## Research

SST-2 - dataset from GLUE with big amount of data-instances

There are following aspects considered in this study:
1. **Representation function** is presented only by Doc2Vec
and is not presented by BERT due to time limitation.
For better performance it is suggestible to apply BERT
representation as well because it is one of the most
advanced model.
2. **Model choice.** is presented within two groups: basic
classifiers and recurrent classifier. Basic classifiers includes LogisticRegression, XGBClassifier, NearestCen-
troid, etc., recurrent classifier is a bidirectional LSTM.
Here we applied different configurations of LSTM architecture but intentionally did not apply high variability of
configurations because we aim to evaluate contribution
of every added parameter and based on contribution
make a conclusion about importance of added parameter.
Explored parameters are: bidirectional or onedirectional
LSTM, dropouts and one additional dense layer with
sorftmax activation between LSTM and output layers.

File ```sst2.ipynb``` reflects all experiments and its performance and file ```GLUE classifier.pdf``` provides with short report with analysis.

## Analysis

SST-2 classification is complicated with amount of data
instances, but despite of this f1-score were achieved up to
0.70.

1. **Model choice.** LSTM model was not able to correctly
classify different classes. Losses values showed LSTM
was overfitted from the early epochs and only learnt to
classify all instances as instances belonging to one class.
No additional parameters improved the performance. It
indicates simple bidirectional LSTM with output layer
is not enough to train a classifier.
