# What does Naive Bayes know about (Bumble) dating reviews? - NLP
- Here I explored 2000 Bumble dating reviews from the Apple app store in this project. I wanted to make a model that could determine whether a review was good or bad (here I decided that a good review was 4 or more). I also wanted to see which words occurred the most for different ratings.
- So I started by doing some exploratory data analysis using Python libraries such as Seaborn, Matplotlib, Pandas and NumPy. My first task was to work out how many 1 to 5-star reviews there are.
- Using Python this is easy to find and as we see in this first image there are a large number of 1-star reviews. This will be taken into account when considering the accuracy of the model later on.

![](Picture_10.png)

- Now before using NLP I wanted to see if the length of the title or review had any correlation with the rating of the review. So I decided to introduce two new columns to the data frame which are the review length and title length columns. If you look at the length of the reviews for the different ratings you can see that typically the reviews with lower ratings are longer. The box plot below shows just this. It is also the case that the titles are slightly longer for reviews with lower ratings but the correlation for this is weaker than for the review length.

![](Picture_11.png)

- The first model that I use here is Naive Bayes.
- Before starting to make the model I first made a new column which is a 1 if the review is 4 or more and 0 if the review is less than 4.
- To make the model I started by using sklearn's CountVectorizer which I fitted and transformed to the reviews variable.
- Then using sklearn's train test split and MultinomialNB I was able to predict if a review was good or not.
- This model has an accuracy of **0.83**. This is better than if we had made the guess that all the reviews are bad which has an accuracy of 0.78.
- Below is the confusion matrix for the Naive Bayes model. 

![](Picture_12.png)

- The second model I tried out is a random forest classifier.
- For this model, I also imported stopwords from nltk and string. I used these to make a function which can remove punctuation and stopwords from the reviews as I thought that this might improve the accuracy of the model.
- Then I imported the TfidfTransformer, the Pipeline and the RandomForestClassifier from sklearn.
- Once I fitted and predicted using the model, the classification report gave the model an accuracy of **0.84** slightly higher than the previous model.
- Below is the confusion matrix for the random forest classifier model. Note this model is more likely to classify good reviews as bad reviews than the previous model.

![](Picture_13.png)

- To find what the most popular words are for different ratings I used a word cloud. 
- The first word cloud here is for reviews with a rating of 1 star.

![](Picture_14.png)

- The second word cloud here is for reviews with a rating of 5 stars.

![](Picture_15.png)

- If I was to spend more time on this project I would look into improving the different model's performances by adding in some additional features like the length of the review and title. I would also use the same models but with the title text instead of the review text.
- Additionally, I would do a more sophisticated word count as this would be beneficial from a business intelligence point of view to understand what people like and dislike about the app. Knowing this could help Bumble improve certain aspects of the app which would improve their reviews and their overall performance in the dating market.
