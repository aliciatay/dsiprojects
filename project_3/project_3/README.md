# Project 3 - Web APIs and Classification: Suicide vs Depression on Reddit

## Background

The link between suicide and depression is well documented through statistics and research.

However, to say that depression is the cause of all suicides is a misguided generalisation repeated many times too often.

Given the turbulent year exacerbated by the outbreak of Covid-19, mental health cases are expected to increase. The World Health Organisation (WHO) initiated a study to understand the intricate differences between the two illnesses, with a goal to identify and separate potential suicide cases from depression cases accurately, thus directing resources quicker.

## Business Statement

As a team of data scientists engaged by WHO, our objective is two-fold:

* Build a model that accurately seperates suicide-related posts from depression-related posts from Reddit. While both illness are considered important, suicide-related content are time crucial.
* Give insights to the behavioural differences between both illnesses. Exemplify insights with the type of language usage, and list out tips to Reddit moderators on how to identify posts with suicidal intention.

## Data, Metrics, Methods & Models

* Data: From Reddit
    - r/depression
    - r/SuicideWatch
* Metrics: F1 score is selected because the cost of False Negative and False Positives are high. Precision and Recall are needed to correctly predict a case that involved a time-crucial element.
* Model: 3 models were tested
    - Logistic Regression
    - ExtraTrees
    - Multinomial Naive Bayes
* Methods:
    - Data was pulled and cleaned via Reddit's API
    - Modelling:
        1. All models were tested with CountVectorizer and TF-IDF, and then performed with hyperparameter tuning with GridSearch
        2. Models were evaluated based on f1 test score

## Findings
1. About the model
    * Multi NB model, as commonly known for this prowess in text classification, has proven to be the best model in terms of highest in accuracy and f1 score performance
    * The model achieved a 0.673469 score in test accuracy, and 0.687500 in test F1 score.
2. About the Data
    * Commonalities in the choice of words
        - Words such as 'life', 'want' ,'know', 'get' appears often in both subreddits. Even those less frequent words such as 'fucking','something', 'anymore' also appear in equal count on both threads
        - One building point from the insight above is that while subreddits may share common words, this does not in any way signify common intentions. 'want' appears more in r/SuicideWatch because it always almost pairs with 'kill', stringing the post to 'want to kill myself'. 'want' appears more in r/depression relates to'get better' or 'want to live', not explicitly carrying out the act of attempting suicide.
        - Another commonality between suicidal and depressed people is where they tend to relate back to 'life' while penning their posts, and the usage of 'want' connotes a strong desire (either for things to get better in most r/depression posts, or for them to die, mostly in r/SuicideWatch posts.)
        - Similarly, both threads often draw connections to social ties, such as 'family', 'friend', college'. Despairingly, it is often the lack of support from social ties and close connections that sparks the trigger for dark thoughts.
    * Differences in the choice of words:
        - It is interesting to note that only the Suicide WordCloud (albeit appearing less frequent than I had expected it to be) contains the word 'kill', unlike the Depression WordCloud. (Both reddits had the word 'die', which is rather expected)
        - Suicide Reddit has more frequent occurences of words that connotes finality, eg 'gone' ,'done','last'and 'want end','want die', and also darker emotions ie 'want kill', 'fuck fuck', 'going kill'.These words expresses extremity and dosed with more drama, ie 'nothing nothing nothing'. It exemplifies feelings of helplessness, hopelessness and worthlessness for the entire span of remaining life.One possible reason for such strong language could be the need for authors to justify their suicide intention away from social judgement (suicide commonly is an act that lacks social approval, and in some countries like Singapore, legal approval). They need to prove how worthless/void of hope their life is.
        - The Depression Reddit had more words which describes feelings instead, eg 'sad','anxiety','don't know' and contextual words like 'jobs','sleep','random', 'coffee'. There is a degree of hope in their posts, and a desire to make things still get better. Choice of diction in this subreddit may crudely be summarized as aggressive self-pity and abject self-loathing. Authors tend to share songs and stories more, seemingly more at tantrum with a moment of life, rather than its entirety
    * Looking at the Word Counts
        - Suicide authors tend to write 100 words lesser on the average. This could be due to the dominant style of narrative writing on r/depression, narrating their life events, while suicidal authors seemingly have very focused thoughts on killing themselves, thus not finding the need to narrate about their life situation
        - While I had expected more comments to be posted to SuicideWatch thread as the posts there would be more alarming and disconcerting, thus triggering more concern, the average number of comments received for both threads is around 1 comment lesser for r/depression only
    * Investigating on the common behaviour from both subreddits
        - There are around 5% of authors who post both on r/SuicideWatch and r/depression threads.
        - However, these authors do not post the same story/submission to the two threads
        - For words that appear on both subreddits(ie want kill, want die), the distintion between the two threads are the frequency of such words (ie 'want die' appears more than x2 in r/SuicideWatch), and the content differs (ie r/Depression posts more likely as story-telling, while r/SuicideWatch are mostly isolated dark thoughts)

## Future Improvements
1. More Data
    * APIs such as Pushshift can help circumvent the limit of pulling >1k posts
    * More submissions can help to train the model more accurately

2. Exploring other models and NLP libraries
    * More advanced libraries such as Spacy/ Word2Vec may improve the model's understanding of contextual language, especially given how both threads have such similar category of dark thoughts
    * Other models such as SVM/AdaBoost can also be further explored
