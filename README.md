## AffinityAnswers

#### Assesment

* The Twitter tweets are stored in a text file, with each tweet on a new line.
* The set of racial slurs is provided in a text file, with each slur on a new line.
* We will consider the degree of profanity to be the number of racial slurs present in a tweet.
* We will ignore case sensitivity.

```python
	# Open and read the file containing tweets
with open('tweets.txt', 'r') as f:
    tweets = f.readlines()

# Open and read the file containing racial slurs
with open('slurs.txt', 'r') as f:
    slurs = set([slur.strip().lower() for slur in f.readlines()])

# Loop through each tweet and count the number of slurs present
for tweet in tweets:
    count = 0
    words = tweet.strip().lower().split()
    for word in words:
        if word in slurs:
            count += 1
    print(f"Tweet: {tweet.strip()} | Profanity level: {count}")
```

> The program first reads the text file containing tweets and stores them in a list. It then reads the text file containing racial slurs and stores them in a set after stripping whitespace and converting all slurs to lowercase for case insensitivity.

> The program then loops through each tweet and splits it into individual words. For each word in the tweet, it checks if it matches any of the racial slurs in the set. If it does, it increments the count of profanity for that tweet. After checking all words in the tweet, the program prints the tweet and its corresponding profanity level.

##### Note that this program does not take into account any variations or misspellings of the racial slurs, and it does not handle cases where a word that could be a slur is used in a non-offensive context. Therefore, the results should be taken as a rough estimate of the profanity level in the tweets.
