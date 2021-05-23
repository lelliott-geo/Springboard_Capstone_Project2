# Springboard_Capstone_Project_2: Automated Tagging of Stack Exchange Data Science Posts Using Natural Language Processing

# Problem Definition

For many question answering websites (Stack Overflow, StackExchange, Quora, Answerbag, Yahoo, WikiAnswers, etc.), a plethora of questions on many different subjects are submitted each day.  On Stack Exchange, each question requires at least one tag to provide context for and to categorize that question. These tags are an important ranking factor in most of these website’s  search algorithms, so it is important for them to be as accurate as possible in order to ensure the best customer experience.  The more quickly and accurately the tags can be assigned, the better the service can be about sending the right question to the right set of people for answering and the quicker the turnaround time for an answer to that question.  The tags also provide the users with the ability to sort and filter through questions and answers on their topic of concern. 

As of 2011, Stack Exchange used a 2-step process to assign tags (https://stackoverflow.blog/2011/08/09/improved-tagging/#:~:text=But%20how%20do%20you%20determine,what%20you've%20typed%20so%E2%80%A6&text=%2DFounder%20(Former)-,Every%20Stack%20Exchange%20question%20is%20required%20to%20have%20at%20least,%2C%20order%2C%20and%20find%20questions.).  First, a recommender engine (tag completer) is used to suggest tags to the question asker based on the question text.  Then the question asker chooses the best tags (minimum of one, maximum of five).  A set of guidelines is provided. But tag selection can be challenging for inexperienced users and poor tag choice can affect the user’s overall experience.  With a site launch only 7 years ago, a subject that is gradually increasing in popularity and a total of only 100k users to date, it is fair to say that many Stack Exchange Data Science users are relatively inexperienced.

# Approach
The objective of this capstone is to build an algorithm employing natural language processing techniques to automatically predict the tags using the text in the questions themselves, thereby reducing the need for human intervention and making the process of answering questions more efficient.

The client could be a Stack Exchange Data Science site developer (or other question answering entity in the Machine Learning and Data Science domain) who is looking for a faster and more accurate way to automatically tag questions.  Based on the results of this analysis, the client may decide to deploy this new algorithm for auto-tagging questions in order to improve the efficiency of his team and the customers’ experience.

The algorithms used for the project are supervised multi-classification learning types, because each question in the dataset is labelled with at least one tag and the goal is to identify the most pertinent tags from a list of multiple tags.

In order to identify the best algorithm, three different types of text to numeric transformations will be used and three different machine learning algorithm types will be employed.  The different models / transformations will be compared against one another using a ROC - AUC scoring technique (Area Under the Receiver Operating Characteristic Curve) to statistically summarize results for all labels and therefore determine the most accurate method overall.

# Results and Conclusions

The ROC-AUC scores on the test dataset, using the six candidate models selected, range from 85-88% with overfitting ranges of 2-5%.  These positive results indicate that a new method of automated tagging of the primary tag on Stack Exchange Data Science is viable.  

Three different text to vector processes were tested.  The success of these vectorization processes is dependent on the model used.  For Random Forest modelling, the TF-IDF method produced the highest scores.  For Bernoulli Naive Bayes modelling, the Doc2Vec method produced the highest scores.  And for the LGBM modelling, the count vectorization method produced the highest scores.  

Since we have found now that the LGBM model is preferred to use going forward, it may be wise to perform further hypertuning of the count vectorizer and tf-idf transformations using this model instead of the random forest model used in this capstone project. We could also benefit by hypertuning the Doc2Vec transformation further to reduce overfitting.

The LGBM method produced both the highest ROC-AUC scores on the validation set and the lowest overfitting percentage, making it the preferred model over the Random Forest and Bernoulli Naive Bayes techniques. The LGBM algorithm also gave us the flexibility to regularize the algorithm better.  Since it runs fast, experimentation was easier.

A next step would be to work to build a model that can predict multiple tags now that we’ve succeeded at predicting the first most popular tag.  A possible additional task would be to create our own NER dictionary of Data Science terms to improve the results of the Named Entity Recognition process.

# Repository Structure

# CP2_01_Convert XML to DF.ipynb
# CP2_02_Load DF Clean and Analyze.ipynb
# CP2_03_Clean_Body_Text.ipynb
# CP2_04_Analyze_Features.ipynb
# CP2_05_Transformations.ipynb
# CP2_05_Transformations.ipynb
# CP2_06_RandomForestModelling.ipynb
# CP2_07_LightgbmModelling.ipynb
# CP2_08_BernoulliNaiveBayes.ipynb
# Springboard_Capstone_Project_2_Milestone_Report1.pdf
# Springboard_Capstone_Project_2_Milestone_Report2.pdf
# Coming Soon! The Final Report
# CP2_Final_Presentation_LAE.pdf
