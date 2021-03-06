# Article.RDP.Python.PredictingM-ATargetsUsingML-UnlockingThePotentialOfNLPBasedVariables

## Overview
In this article, I extend on the Mergers and Acquisitions (M&A) predictive modeling that has been [published earlier](https://developers.refinitiv.com/en/article-catalog/article/prediction-of-m-and-a-targets-to-generate-portfolio-returns) by incorporating Natural Language Processing(NLP) based news sentiment variable into it. The original model uses only financial variables and utilizes Logistic regression for M&A target identification and showcases if that will produce an abnormal return for investors. Instead, the purpose of this article is to test if news sentiment derived by NLP has any significant contribution to M&A predictive modeling. To do that, the significance (by comparing evaluation metrics) of news sentiment is tested on different Machine Learning (ML) models, including logistic regression, random forest, and XGBoost models. As it comes to the NLP model, [Finbert](https://huggingface.co/ProsusAI/finbert) and [BERT-RNA](https://www.lseg.com/about-lseg/labs/financial-language-modelling) models are tested to calculate sentiment on the news preceding M&A announcement. 

The motivation behind using the news sentiment variable comes from a literature finding suggesting that target companies generate significant run-up returns during one month before the announcement of the deal. The problem here is that abnormal returns may happen not only because of potential future merger announcements but also because of other good news impacting the share prices. Thus, overall news sentiment should be evaluated and discussed in relation to the abnormal return. Our hypothesis here is that only abnormal return amid no or low positive news sentiment environment is an indication of M&A announcement.

## Structure
The article has the following structure. In Section 1, datasets of target and non-target companies are constructed. The article utilizes Refinitiv Data Platform (RDP) API to access the required data. For the target datasets, the RDP search function is used to get the list of target companies for the specified period, and for non-targets, I use the PEER screen function to request peer companies of the target list. Financial variables for both target and non-target companies are requested via the get_data function. In section 2, news sentiment prior to M&A is calculated via NLP techniques. Finally, in section 3, the performance of different ML models with and without news sentiment variable, calculated both by FinBert and BERT-RNA models, is evaluated.

## Dependencies

* Python library 'refinitiv.dataplatform' version 1.0.0a8.post1
* Python library 'pandas' version 1.3.3
* Python library 'numpy' version 1.20.1
* Python library 'Sklearn' version 0.24.1
* Python library 'huggingface_hub' 0.0.19
* Python library 'tokenizers' 0.10.3
* Python library 'torch' 1.9.1+cpu
* Python library 'transformers' 4.11.3
* Python library 'xgboost' 1.5.0
* Python library 'plotly' 5.3.1
