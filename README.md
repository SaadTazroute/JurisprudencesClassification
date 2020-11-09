## Jurisprudences Classification

This project consists in carrying out a classification of the decisions of the French Court of Cassation carried out within the framework of a research internship,  you'll also find the paper I was able to write during this period of lock down and internship.

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


The Colab link is on the top of each notebook.
You will find 4 notebooks in this repository, you can run it on your local machine, or on colab:
	
	00 : Creation of the file which gathers all the cases. 
	01 : Deep Analysis of the french Cass Dataset 
	02 : Classifier : TF-IDF + ML Algorithms
	03 : Classifier : CamemBERTforSequenceClassification
	
	
	
	
How to use it  : 

* Download the data from [this link](https://echanges.dila.gouv.fr/OPENDATA/CASS/)
* Execute 00 locally using Jupyter notebook, it will take as input the folder downloaded, and allows you to create a .csv file containing all the case law.
* Upload the csv file (named in the notebooks freemium02) on google drive to mount it into drive easily.
* execute the 01, 02 , 03 in the order you like.

#### Problem formulation : Multi-class Text Classification

Let's consider a data set D containing sequences of text samples : 


$$  D = D_1,D_2 , \dots, D_N  $$

We consider also a set of labels denoted as: 

$$ Y = Y_1,Y_2 , \dots, Y_M$$
\begin{itemize}
    \item  Where $D_i$ is the $i^{th} $ sample of our data set, which can be a document, a text segment.

    \item $Y$ is a set of unique labels and $M$ is the number of labels in the data set.
\end{itemize}

Classification is the task of approximating a mapping function ($f$) from input variables ($D$) to discrete output variables ($Y$):
$$ f(D)=Y $$


In this paper, we consider that we want to classify the different documents of our data set, in other terms each row is a single document. 

Each document has a unique class to which it belongs.

#### Methodology : 

Gathering dataset from [the French Court of Cassation's database](https://echanges.dila.gouv.fr/OPENDATA/CASS/)

Use 2 different approachs to manipulate this data.

## Bag of words + TF-IDF Score :  

The first one is the bag of words paradigm + A TF-IDF scoring + Machine Learning algorithm

\begin{itemize}
    \item \textit{TF}: Term Frequency, which measures how frequently a term occurs in a document. Since every document is different in length, it is possible that a term would appear much more times in long documents than shorter ones. Thus, the term frequency is often divided by the document length (aka. the total number of terms in the document) as a way of normalization:
    
    $$ tf_{i,j} = \frac{|\{t_i : t_i \in d_{j}\}|}{|d_{j}\|}  $$
\begin{itemize}
    \item $ |\{t_i : t_i \in d_{j}\}| $ : Number of times term $t_i$ appears in a document $d_j$
    \item $ |d_{j}\| :$ Total number of terms in the document $d_j$
\end{itemize}



    \item \textit{IDF}: Inverse Document Frequency, which measures how important a term is. While computing TF, all terms are considered equally important. However it is known that certain terms, such as "is", "of", and "that", may appear a lot of times but have little importance. Thus we need to weigh down the frequent terms while scale up the rare ones, by computing the following:

$$ \mathrm{idf_i} =  \log \frac{|D|}{|\{d_{j}: t_{i} \in d_{j}\}|} $$

The second one is CamemBERT for text classification, which is a pretrained neural network

## 

	
