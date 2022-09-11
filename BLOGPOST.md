# Can we predict a movie rating with data?

Maybe. Let's find out! Spoiler alert: it's difficult.

![Disaster Response Project](https://github.com/aivoric/MovieAnalysis/blob/main/images/prediction.jpeg?raw=true)

### A huge growth in the number of movies

In the last couple of decades the number of movies released world wide has been growing at a very rapid pace.



![Disaster Response Project](https://github.com/aivoric/MovieAnalysis/blob/main/images/us-uk-movie-releases.png?raw=true)
Source: https://stephenfollows.com/how-many-films-are-released-each-year/

It is becoming more and more difficult to choose a movie to watch. People more often now are starting to rely on
movie ratings in order to determine whether they should watch a certain movie not.

However, when there is no rating yet (for new movies) it's difficult to say whether it will be a success or not.

### Netflix

Netflix is an obvious place to go to if you are looking for something to watch.

Fortunately the company has provided a full data set of their movies with IMDB ratings and various other interesting
data points in July 2022. This can be found here:
https://www.kaggle.com/datasets/victorsoeiro/netflix-tv-shows-and-movies

Using this data we can try and answer the question posed above: "Can we predict a movie rating with data?". But before
we do that let's explore a few other questions to familiarise ourselves with the data we have.

### So what do people actually like to watch?

![Most and least popular genre.](/images/genres.png?raw=true "Most and least popular genre.")

Interestingly we see that drama and comedy top genre popularity movie charts. Most likely for their neutrality, i.e. it is
about day to day life (very often). These genres don't traverse into realms we rarely live in. These realms can be easily
seen in the least popular genres of "western" and "war". Which makes sense. After a hard day at work, are you really going
to watch a war movie or a western movie (which also tends to be brutal)?

### Who are those actors which play in the most amount of movies and tv show on Netflix?

Looking at the actors which played in the most amount of movies and tv shoes on Netflix we find:

![Most popular actors.](/images/actors.png?raw=true "Most popular actors.")

Surprisingly (or not) we will actually find a lot of Eastern names (of Indian origin primarily). Actually this is not so surpsing because
Bollywood is HUGE! And Netflix has been partnering a lot with movie producers in India.

If we zoom into the most popular directors we see the following:

![Most popular directors.](/images/actors.png?raw=true "Most popular directors.")

Raul Campos? Ever heard of him? I certainly haven't. Let's check him out:
https://www.imdb.com/name/nm6875068/

And Jan Suter?
https://www.imdb.com/name/nm5158437/

It looks like both are producing a lot of content geared towards spanish speaking audiences.

Very interesting...we have indian actors playing in the most amount of movies / tv shoes, and the top 2 producers are
churning out content for the Spanish speaking audience.

### Can we predict a movie rating, and if so, how?

This is a very difficult question. There are obviously many factors which influence whether a movie will score well (or not).

But let's give it a shot.

So the question to ask is: what serves as a good predictor of a movie score? Let's try to use the following as predictors:
* Production country
* Genre
* Runtime
* Release year
* Age-certification
* Actors

Generally quite straight forward. I am sure we can think of other data which would impact a movie rating. However, in the above
one data point "Actors" is not as simple as it sounds. The basic premise is: does the presence of a certain actor in a movie
impact its rating? e.g. if Leonardo di Caprio plays in a movie, will that movie score higher? 

There are thousands of actors, and therefore if we try to build a model which tries to use the actors data, the model complexity grows.
This was the case with my model too.

I ended up with a table which has 54087 columns and 74140 rows. Crazy, right? Basically there is 1 column to represent whether an actor
is present in a movie or not (this uses some hot encoding magic):

![Big Table.](/images/big-table.png?raw=true "A big table with a lot of actors.")

Since we have so many columns relative to the number of rows the model is unlikely to fit well.

Let's try fit the model with XGBoost anyway. What is XGBoost and why use it?

It's unversal algorithm which has won many kaggle competitions. It can be used for many diverse purposes.

Let's steal the description from the official website:

https://xgboost.readthedocs.io/en/stable/
"XGBoost is an optimized distributed gradient boosting library designed to be highly efficient, flexible and portable. It implements machine learning algorithms under the Gradient Boosting framework. XGBoost provides a parallel tree boosting (also known as GBDT, GBM) that solve many data science problems in a fast and accurate way. The same code runs on major distributed environment (Hadoop, SGE, MPI) and can solve problems beyond billions of examples."

![XGBoost.](/images/xgboost.jpeg?raw=true "XGBoost as .")

So what happens when we try to train a model using the Netflix data set? Can the model be used to predict movie ratings?

So in short: maybe. When you calculated the mean squared error (sorry, getting technical here) you get: TBD.

There may be some predictive value in the model, but as mentioned above, we would need to revisit the data engineering side
of this project to see if can group the data somehow differently to product a different input for the model.

### Thank you

Thank you for reading this. Hopefully you find some interesting insights.