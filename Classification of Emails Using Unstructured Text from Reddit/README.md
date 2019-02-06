File Directory:

1. README.md - Outlines obectives, data, methodology and next steps of analysis. 
2. Hoppes LLC Religion Classification Results.pdf - An presentation outline of key findings with visuals that explain problem statement and results.
3. project 3.ipynb - Python notebook with code used in processing text and analyzing results of our email classification algorithm.


Objective: After finishing up successful campaigns at the College Board and Zillow, word of Hoppes LLC’s data science prowess has been traveling far and wide. So far and wide that one day you get a  call from Canada’s largest and longest multi-faith event, the World Religions Conference. 
Johnny Doe’s job was to work with IT to set up religion specific email addresses and update the marketing materials with those email addresses so the thousands of conference attendees could follow with presenters and organizers. This is especially important as this is the year’s flagship event that generates a disproportionate amount of connections, and it is imperative that the religion divisions be able to respond quickly. 
Johnny was feeling the pressure, and he was in such a rush that he forgot to update the materials for the Buddhism and Christianity, religions that total a combined 2.7 billion devotees world wide. These events usually generate 1,000s of emails and now they will be jumbled and unorganized in a general inbox. The Christianity and Buddhism divisions are freaking out, and needless to say Johnny was relegated back to coffee duty for the remainder of his summer. 


Data:
When they called Hoppes LLC, they stressed the problem was extremely urgent and that we needed a classification algorithm to be working right away. 
Because you don’t have access to their emails, and the request is time sensitive, you have another idea. You check reddit, and it looks like they have about 150-170K subscribers a piece and are fairly active. You explain to the client that this is a robust enough set of posts to train a model on.
Being a religious organization and knowing Reddit’s reputation they were squeamish, but obliged.

www.reddit.com/r/Christianity

www.reddit.com/r/Buddhism

In order to gather a large amount of Reddit data Hoppes LLC decided to use the Reddit Pushshift API, which allows developers to pull posts from the full database of Reddit activity. 
Using this method you convert the data into a dataframe with 7,857 posts from r/Christianity and 6,578 posts from r/Buddhism.

|Feature|Type|Description|
|---|---|---|
|**title**|*object*|Subject of the reddit post| 
|**selftext**|*object*|Content of the original reddit post|
|**subreddit**|*object*|Either Christianity or Buddhism|
|**created_utc**|*int64*|unique post id|
|**author**|*object*|Reddit handle of the post author|
|**num_comments**|*int64*|Number of comments on the original post|
|**score**|*int64*|Score rewarded for posting popular content|
|**is_self**|*bool*|True or False that the post is the original|
|**timestamp**|*object*|Date when the post was created|




Methodology:

Data Cleaning and Transformation
After the data was collected from the PushShift API, Hoppes LLC executed a list of 
cleaning tasks to make a corpus of words suitable for prediction. Those cleaning tasks included:

1) Concatenate the Christianity and Buddhism tables together.
2) Make an extra field combining the title and post text
3) Instantiate a list to append words back to
4) Use the split method to split each text block into a list. 
5) Remove all numbers
6) Remove all punctuation
7) Ensure that the words are all lower case
8) Remove all stop words (Including customized stop words)
9) Lemmetize the words


Conclusion
With an improvement of 35% over the baseline our classification model has created value 
for the conference, as we can automatically classify nearly 9 out of every 10 emails that were
misplaced in the inbox. This will automate much of the manual work it would take to sort out the emails individually.


Next Steps
1. Do a full pipeline and gridsearch with other classification methods
2. Take a larger set of posts w/ years of data
3. Be more stringent about stopwords
4. Look into comment text associated with a given post




