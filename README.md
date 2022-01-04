# Article.RDP.Python.PredictingM-ATargetsUsingML-UnlockingThePotentialOfNLPBasedVariables

## Overview
In this article, I extend on the Mergers and Acquisitions (M&A) predictive modeling that has been published earlier by incorporating Natural Language Processing(NLP) based news sentiment variable into it. The original model uses only financial variables and utilizes Logistic regression for M&A target identification and showcases if that will produce an abnormal return for investors. Instead, the purpose of this article is to test if news sentiment derived by NLP has any significant contribution to M&A predictive modeling. To do that, the significance (by comparing evaluation metrics) of news sentiment is tested on different Machine Learning (ML) models, including logistic regression, random forest, and XGBoost models. As it comes to the NLP model, Finbert and BERT-RNA models are tested to calculate sentiment on the news preceding M&A announcement.

The motivation behind using the news sentiment variable comes from a literature finding suggesting that target companies generate significant run-up returns during one month before the announcement of the deal. The problem here is that abnormal returns may happen not only because of potential future merger announcements but also because of other good news impacting the share prices. Thus, overall news sentiment should be evaluated and discussed in relation to the abnormal return. Our hypothesis here is that only abnormal return amid no or low positive news sentiment environment is an indication of M&A announcement.

The article has the following structure. In Section 1, datasets of target and non-target companies are constructed. The article utilizes Refinitiv Data Platform (RDP) API to access the required data. For the target datasets, the RDP search function is used to get the list of target companies for the specified period, and for non-targets, I use the PEER screen function to request peer companies of the target list. Financial variables for both target and non-target companies are requested via the get_data function. In section 2, news sentiment prior to M&A is calculated via NLP techniques. Finally, in section 3, the performance of different ML models with and without news sentiment variable, calculated both by FinBert and BERT-RNA models, is evaluated.
