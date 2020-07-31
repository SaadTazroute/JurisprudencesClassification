## Jurisprudences Classification

This project consists in carrying out a classification of the decisions of the French Court of Cassation carried out within the framework of a research internship,  you'll also find the paper I was able to write during this period of confinement and internship.

#### Abstract


In this article, we examine the application of text classification approaches to assist
legal professionals. We present several experiments applying classification techniques to
predict the French Court of Cassation ruling and the area of law to which a case belongs.

We work on the CASS data set, composed of the judgments of the French Court of
Cassation, containing the body of case law, and the ruling decision and others informations.
We use two methods for classification. The first one is based on the TF-IDF score for
feature extraction from the law text, we used these features as entries to several machine
learning algorithms. The second method consists of using a pre-trained model to extract
features named BERT based on Transformers architecture, and specially its French version
named CamemBERT. We used especially in this paper the stacking of this architecture
and a classification layer to realise the classification task.

Due to resources limitations, we trained the CamemBERT model only on 10 000 case
law.
We report results of 84% F-1 score in predicting a case ruling using CamemBERTforSequenceClassification , 89% F-1 score using the Tf-IDF score and a linear Support Vector
Machine (SVM) classifier trained on lexical features.

The data used is available in this link  : [LegiFrance](https://echanges.dila.gouv.fr/OPENDATA/CASS/)


The Colab link on the top of each notebook.
You will find 4 notebooks in this repo:
	
	00 : Creation of the file which gathers all the cases. 
	01 : Deep Analysis of the french Cass Dataset 
	02 : Classifier : TF-IDF + ML Algorithms
	03 : Classifier : CamemBERTforSequenceClassification
	
	
	
	
How to use it  : 

* Download the data from [this link](https://echanges.dila.gouv.fr/OPENDATA/CASS/)
* Execute 00 locally using Jupyter notebook, it will take as input the folder downloaded, and allows you to create a .csv file containing all the case law.
* Upload the csv file (named in the notebooks freemium02) on google drive to mount it into drive easily.
* execute the 01, 02 , 03 in the order you like.





	
