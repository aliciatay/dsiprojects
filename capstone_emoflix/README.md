# Capstone Project: EmoFLIX
--

## Background
In a world full of choices, isn't it paralyzing to browse through the limitless options of entertainment? Imagine spending 15mins to browse through lists of options and having to give up and go to sleep in the end. That's a waste of time!

In my project, I aim to help entertainment platforms such as Netflix to push out relevant titles to the user. To the user, my EmoFLIX model also helps to automate browsing, while ensuring appropriate recommendations based on how you're feeling.

Afterall, don't all choices we make are based on our feelings?

## Business Statement
My project is two-fold:

    1. Help entertainment platforms such as Netflix, push out relevant titles to the user according to their emotions. 
    This will help in
        - Ensuring that consumer stays in own platform and does not bounce out to competitors' entertainment platforms
        - Increase viewing rates based on relevancy of recommended titles
    2. Help user reduce browing time by automating the process, and also fine-tuning recommendation by customizing titles to their feelings
    
To build this project, I will need to train an emotion facial recognition based on image, and a Netflix title recommender. Both systems will be mapped together eventually.
    
 ## Data
 - Data for Netflix Recommender is taken from Kaggle.
 - Data for Emotion Recognition is taken from Kaggle.
 
 ## Methods
 
 1. Emotion Recognition
    - Trained on 4 models (CNN, VGGFace, VGG16 and ResNet50) to determine best architecture to finetune
    - While VGG16 model performed the best, and CNN model performed the worst, I decided to experiment on CNN given the relatively decent performance albeit a much shallower network
    - Used Optuna and Mixup to bump up CNN's performance by 0.04%
    - Final model (VGG16) was saved and will be subsequently used to predict test images
 2. Movie Recommender
    - Merged IMDB and Netflix datasets as Netflix dataset did not have a rating feature
    - Preprocessed an 'Weighted Average Score' that took into consideration the mean ratings based on minimum vote
    - Engineered a function that returns top titles sorted by the Weighted Average Score, based on a given genre.
 3. Combined Emotion Recommender Model
    - Both models explained in 1 and 2 are combined together to birth 'EmoFLIX'
 
 ## Findings

-  Prediction model used is VGG16, of accuracy 66% (Human accuracy rate was 65%)
-  Given the noisy dataset with corrupt data labels, shallower networks such as CNN of depth 3-5 layers or VGG16 performed with higher accuracy compared to deeper, modern state-of-art architecture such as ResNet50
-  Emotions are hard to predict, as a person could be feeling two emotions at a given moment in time. The tricky part in determining a singular emotion to a facial expression is partly reason to noisy data labels

## Conclusion
Concluding thoughts and project wrap up can be found via the presentation slides here: https://docs.google.com/presentation/d/1TYpSqjJw8RQ8uJDjiuPrU6baDtfBdEY1Qgf41UUIjko/edit#slide=id.gb44639e4bb_0_0
