###### Prerequisite: Please download [Git lfs](https://git-lfs.github.com/) 

```bash
sudo apt install git-lfs
# alternatively (if you don't have root and installed but use conda, see next note about conda environment)
conda install -c conda-forge git-lfs

# in git repo
git lfs install
git lfs pull
```
  
###### Optional: Install conda environment, with jupyter, gensim, nltk, pandas, scikit-learn, ...

```bash
conda env create -f environment.yml
conda activate argmining19-ssc
```
  
# [Same Side Classification](https://sameside.webis.de) 

Identifying (classifying) the stance of an argument towards a particular topic is a fundamental task in computational argumentation. The stance of an argument as considered here is a two-valued function: it can either be ''pro'' a topic (= yes, I agree), or ''con'' a topic (= no, I do not agree).

With the new task » same side (stance) classification« we address a simpler variant of this problem: Given two arguments regarding a certain topic, the task is to decide whether or not the two arguments have the same stance. 
  
## Task: Same Side Classification

Given two arguments on the same topic, decide whether they have the same or opposite stance towards the topic. 


## Settings
We have two experimental settings:
 - Within: Train on a set of topics and evaluate on the same set of topics.
 - Cross: Train on one topic and evaluate on another topic.
We choose the 2 topics with highest number of arguments: *abortion* and *gay marriage*.


## Data
### Data source:
idebate.org, debatepedia.org, debatewise.org, debate.org

The data folder contains the training and testing data, for *cross* and *within* topics. You can split the *training* data as you like in order to train your model. After that, the model will be evaluated using the test data.

## Baseline
We trained a model using lemma 3 grams for argument1 and argument2 on the training set and then we evaluated the model using the test set. The results are the following:

 - Within Topics:
   - 	Accuracy: 54%
   - 	Macro-F1:  0.39
   - 	Micro-F1: 0.54

 - Cross Topics:
   - 	Accuracy: 58%
   - 	Macro-F1:  0.39
   - 	Micro-F1: 0.58
   
For more details, visit https://sameside.webis.de

