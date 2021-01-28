
# General Assembly's Data Science Projects


Welcome to my portfolio of GA projects! <br>
This consists of:
1. Project 1: EDA to uncover insights to increase uptake rates
2. Project 2: Price Prediction
3. Project 3: NLP Classification on Mental Illnesses 
4. Project 4: Neural Networks on Virus Outbreak Prediction 
5. Capstone Project: Entertainment Recommendator System based on Facial Emotion Detection 
6. _(For Fun):_ Multi-Modal Movie Rating Prediction _(ongoing)_
 

### About my repo and I 

>"...whoever controls data controls the world..."

Besides the desire for world domination, I was an integrated marketer who wanted to dig out much more knowledge that was hiding within the mounds of data. So I got my hands dirty and learn the dark arts of Data Science.

This repo stores my first steps into the deep rabbit hole of Machine Learning, where I aim to complete all 5 core projects organized by General Assembly Singapore.

Connect with me if you'd like to hear more: www.linkedin.com/in/aliciataylixian/

## Project 1:  EDA on America's Examinations (ACT & SAT)

Researched on a foreign subject (America's Examination system for two examinations - ACT and SAT) to justified recommendations on increasing student uptake year-on-year.

Highlights:
* Did data wrangling and cleaning
* Performed statistical inferences to clarify data assumptions 
* Created various graphs through APIs such as choropleths via the Plotly library
* Supplemented data with independent sourcing of news on the societal and political changes in America

_Note: Project was issued via a Question- and- Answer format where there was a specific sequence for me to follow_
 
## Project 2: Price Prediction

Given the popular Ames Housing dataset, I had to predict house prices, with the extra challenge of using only classical linear regression models and utilizing only 30 features.

Highlights:
* Data wrangling with various features of high/missing null values
* Feature Elimination with Lasso and Ridge Models
* Hyperparameter tuning with GridSearchCV


## Project 3: NLP Classification of Mental Illnesses

Took a challenge to build a model to classify two mental illnesses well-known for being consequential to each other: Suicide and Depression.

I was personally motivated given the rise in suicidal declarations through social media channels and livestreams. 

Highlights:
* Webscrapped Reddit threads r/SuicidalWatch and r/Depression
* Teased insights through EDA of 1-gram/2-gram and WordCloud visualizations
* NLP techniques such as TF-IDF/CountVec
* Tested on various models such as Multi Naive Bayes, Log Regression and Extra Trees
* Built a model that was 68% accurate in F1 score

## Project 4: Machine Learning on Virus Outbreak Prediction

This was part of a group project, where we worked on a past Kaggle competition for West Nile Virus Prediction.

Highlights:
* Achieved an accuracy score of 77% after model fine-tunning from a group of different architectures (SGD Classifiers/ Log Regression/ Random Forest)
* Did a cost-benefit analysis with case studies from Sacramento and Singapore, to present a business strategy that is backed by model's predictive techniques

## Capstone: Entertainment Recommendation based on Face Emotion Detection: _EmoFLIX_

Leveraging on how decision making are motivated by emotions, I wanted to build a model that could automate browsing on entertainment platforms based on emotion/feelings. 

My project use-value is two-fold:
1. Help entertainment platforms such as Netflix, push out relevant titles to the user according to consumers' emotions. 
This will help in
    - Ensuring that consumer stays in own platform and does not bounce out to competitors' entertainment platforms (is HBO/Disney+)
    - Increase viewing rates due to the relevancy of recommended titles
2. Help user reduce browing time by automating the process, and also fine-tuning recommendation by customizing titles to their feelings

Highlights:
* Trained on 4 model architectures
* Fine-tuned with Optuna (hyper-param package library) and Mixup to push baseline up to 66%, outperforming human accuracy level
* Due to noisy labels, shallower models tend to provide higiher accuracy than compared to deeper, more modern state-of-art architecture
