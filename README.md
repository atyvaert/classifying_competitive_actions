# coding
Github repository: https://github.ugent.be/atyvaert/coding.git

In this GitHub repository, you will find the code accompanying the master dissertation of Artur Tyvaert.
It is important to first read this notebook to gain more understanding about the structure of these notebooks. To find the best-performing approach in this classification setting with respect to the macro-average F1 metric, I conducted an extensive experimental analysis using various text representation methods, resampling techniques, and base classifiers to evaluate the performance of a wide range of different models. Next, I also evaluated the results of two transformer models, which have proven to achieve state-of-the-art performance for various natural language processing tasks.

First, I explored the data in the notebook '0. Data exploration and data splitting.'. In this notebook, I load in the original data and explore the raw data. In this notebook, I give more explanation about the class imbalance issues, the data splitting, and the recategorization of the categories. The recategorized data is stored in 'silver_data'.

Second, I preprocessed and cleaned the data in the notebook 'A. BOW_TF_IDF'. This cleaned data is stored in the 'gold_data' file as this is the data that is used to train the algorithms. Thus, this data is used in the other notebooks to transform the textual data into numerical representations. In this notebook 'A. BOW_TF_IDF', I also evaluate the performance of the base classifier with the text representations methods BoW and TF-IDF as input data. Further, I also give information about the different resampling strategies that are used in this and the following notebooks. This information is not repeated in every notebook, hence, it is important to read this notebook before B, C, D, and E.

Next, I trained the CBOW and SkipGram models in the notebook 'B. Embeddings'. This notebook used the gold data as input data and provides more details about their implementation. Note that the same resampling strategies were used that I explained in notebook 'A. BOW_TF_IDF'. Fourth, the notebook 'C. Pre-trained embeddings' provide more inforamtion about the download and the implementation of the pre-trained embeddings. Further, the same code is used as in the previous notebooks to evaluate these models.

Notebook 'D. Transformers' gives more information about the implementation of the transformer models BERT and RoBERTa with the SimpleTransformers library. It is possible that users have problems installing this library on the M1 or M2 chips of an Apple computer.

Finally, I retrained a random forest classifier with TF-IDF text representations as input data and SMOTE resampling to gain insights into the importance of the different words when classifying competitive actions. The different steps of this procedure are described in the notebook 'E. Keywords'.

# Folders
In this repository, there are 3 main folders. The folder 'src' contains the notebooks that I just described. Second, the folder 'data' contains all the data that has been used in this research. This also contains the 'silver_data' and gold_data' previously discussed. Finally, the folder 'Output' contains the different outputs from all notebooks. First, it contains the class imbalance of the original and recategorized dataset. Next, it contains the predictions on the test set of all the trained models. Moreover, it also contains the results and the optimal parameters for each evaluated model.

# conclusions

The results of my analysis regarding the performance of the different classifiers reveal three main conclusions. First, my findings show that the state-of-the-art transformer models BERT and RoBERTa achieve significantly better performance than the traditional methods. Second, the count-based text transformation methods achieve better performance in general compared to the embedding methods, although the best-performing models have similar results. Third, when inspecting the results of the proposed resampling techniques to deal with the class imbalance issues, random under-sampling decreases the performance of the classifiers, while SMOTE does not improve the results, except with tree-based classification methods.
