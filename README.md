
![Python](https://img.shields.io/badge/python-v3.6+-blue.svg)
[![GitHub stars](https://img.shields.io/github/stars/MauroLuzzatto/Natural-Language-Understanding--Story-Cloze-Task?color=green)](https://github.com/MauroLuzzatto/Natural-Language-Understanding--Story-Cloze-Task/stargazers)
<!-- ![GitHub All Releases](https://img.shields.io/github/downloads/MauroLuzzatto/Natural-Language-Understanding--Story-Cloze-Task/total)
 -->
# Solving the Story Clozed Task

<!-- [![Build Status](https://travis.ibm.com/Mauro-Luzzatto/-Data-Modelling.svg?token=zmafNzx54WQZmTrFgEaV&branch=master)](https://travis.ibm.com/Mauro-Luzzatto/-Data-Modelling)
 -->
 <!-- [![Total Downloads](https://poser.pugx.org/phpunit/phpunit/downloads)](//https://github.com/MauroLuzzatto/Natural-Language-Understanding--Story-Cloze-Task) -->
<!-- [![Github All Releases](https://img.shields.io/github/downloads/MauroLuzzatto/Natural-Language-Understanding--Story-Cloze-Task/total.svg)]()
 -->
<!-- [![Downloads](https://pepy.tech/badge/video2tfrecord)](https://pepy.tech/project/video2tfrecord) -->
<!-- https://img.shields.io/github/stars/MauroLuzzatto/Natural-Language-Understanding--Story-Cloze-Task
 -->


The target of this NLP project was to successfully solve the story cloze task. This task was developed to measure advanced commonsense understanding within everyday written stories [1]. To solve the task, one has to determine the correct ending sentence out of two available options, given the four initial context sentences of the story. 

In the LSDSem 2017 competition, in which different teams competed to solve the story cloze task, validation accuracies between 0.595 and 0.752 were reached [2]. The major difficulty of this task is to extract semantic information from the story context and use it to determine the correct ending.


 Our ﬁnal model relies on a combination of features derived from word and sentence embeddings, as well as from predicted sentence embeddings from a generative RNN. The features are fed into a logistic regression model to perform the classiﬁcation. The ﬁnal implementation was able to reach a validation accuracy of 71% which is near the state-of-the art solutions scores [4].


The following datasets were provided:

### Training Set
* the frist consisted of the context sentences with the correct ending only: [train](/data/train_stories.csv)
* the second included an additional incorrect ending to the correct one: [validation 1](/data/cloze_test_spring2016-test.csv)

### Evaluation Set
* an evaluation set [validation 2](/data/cloze_test_val__spring2016_cloze_test_ALL_val.csv) with context sentences and labeled endings to determine the accuracy of the classifier

### Test Set
* a test set [test](/data/test_nlu18_utf-8.csv) to participate in the competition by classifying unlabeled sentences



### Sources:
[1] Nasrin Mostafazadeh et al. A corpus and cloze evaluation for deeper understanding commonsense
stories. 2016.
[2] Nasrin Mostafazadeh et al. Lsdsem 2017 shared task: The story cloze test. 2017.
[3] [Story Cloze Test and ROCStories Corpora Description](http://cs.rochester.edu/nlp/rocstories/)
[4] [Final Project Report](/Report/20180608%20-%20Final%20Project%20Report.pdf)


(Date: 30.05.2018)

## Getting Started
1. Install dependencies by running: `python3 setup.py install`

2. Run `word2vec.py` to create the word emebeddings. They will be saved and reloaded for further task. The code is taken from: https://github.com/tensorflow/tensorflow/blob/r1.8/tensorflow/examples/tutorials/word2vec/word2vec_basic.py

3. Run `main_story_clozed_task.py` with the training_mode rnn option set to true. The first run will take a couple minutes because multiple embeddings will have to be loaded and calculated.

4. Run 'main_story_clozed_task.py' with the training_mode rnn option set to false. The model will predict on the validation set and display the validation accuracy. A output file containing predictions on the test set is saved in the current folder.

## Authors
* **Mauro Luzzatto** - [Maurol](https://github.com/MauroLuzzatto)
* **Dario Kneubuehler** - [Darkneu](https://github.com/Darkneu)
* **Thomas Brunschwiler**