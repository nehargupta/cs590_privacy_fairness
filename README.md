# A perturbation and threshold analysis of fairness in text classification
Suppose you have a website. And a comments section, where users can leave comments.

When users leave comments, we may want to flag some comments as toxic, and choose not to publish them. We may want to do this with a classifier.

We have a dataset of Wikipedia Talk Page comments. Unfortunately, since there are many toxic comments containing demographic identity terms, like the term “gay”, a classifier may also flag non-toxic uses of the term “gay” as toxic.

We’d like to flag comments like “Gay people are awful!!!”.
But we don’t want to flag comments like “I am a proud gay person”.

Dixon et al (2017) tackle this problem.

Our project seeks to shed light on:

1) The association between bias in a text dataset and the bias of a classifier trained on that dataset. Does a classifier exacerbate changes in the bias of its input data?

   We measure bias with a variant of disparate impact, for a nonbinary protected attribute. The classifier labels toxic comments. It is a simple logistic regression classifier found [here](https://github.com/ewulczyn/wiki-detox/blob/master/src/figshare/Wikipedia%20Talk%20Data%20-%20Getting%20Started.ipynb) in the ConversationAI project.

2) How that association is affected by changes in the mean toxicity rating threshold for labeling a comment as toxic. Is the classifier, and the fairness of its predictions, robust to changes in this threshold? How sensitive is it to these changes?

This is a team project for CS-590.1 (Differential privacy and fairness in machine learning and data science), at Duke University. Fall 2018.

# Approach

First, we measure bias. Second, we perturb our dataset, and then look at the relationship between the bias of each perturbed dataset and the bias of a classifier trained on that perturbed dataset. Third, we alter the mean toxicity rating threshold for labeling a comment as toxic, and look at how this threshold is associated with the bias of our trained classifier.

# Results

1) It appears that, with our method of perturbation and the classifier we use, as the bias of our dataset increases, the bias of a classifier trained on that dataset increases, but at a decreasing rate.

2) As we increase the mean toxicity rating threshold, the bias of our classifier increases.
