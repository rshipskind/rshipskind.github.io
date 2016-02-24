---
layout: post
title:  "Comparative Netflix Ratings"
date:   2016-02-23 00:23:21 -0500
categories: blog
---

I often find myself rating a Netflix show after watching it with my wife. Unfortunately, I find myself frequently giving harsher ratings than she does. So, one weekend while she was out of town, I decided to empirically prove that she was systemically inflating her ratings. Luckily, exporting our ratings was made simple with the help of [Flix Plus](https://github.com/jaredsohn/flix_plus).

Once the json files were downloaded it was a simple matter to graph the relative amount of our ratings each star received.

```python
import json
import matplotlib.pyplot as plt
import seaborn as sns
from collections import Counter
import numpy as np
%matplotlib inline

# imports json data
json_one = input("Filepath to first account JSON: ")
user_one = input("User one: ")
json_two = input("Filepath to second account JSON, or 'pass': ")
if json_two != 'pass':
    user_two = input("User two: ")

with open(json_one) as data_file:
    data_one = json.load(data_file)

# counts occurrences of each rating and total number of ratings    
ratings = Counter()
for i in data_one:
    rating = int(i['yourrating'])
    if rating == 1:
        ratings[1] += 1
    elif rating == 2:
        ratings[2] += 1
    elif rating == 3:
        ratings[3] += 1
    elif rating == 4:
        ratings[4] += 1
    elif rating == 5:
        ratings[5] += 1
ratings_count = sum(ratings.values())

# converts Counter to percentages
ones = ratings[1] / ratings_count * 100
twos = ratings[2] / ratings_count * 100
threes = ratings[3] / ratings_count * 100
fours = ratings[4] / ratings_count * 100
fives = ratings[5] / ratings_count * 100

# repeats prior steps if a second json file is passed
if json_two == 'pass':
    pass
else:
    with open(json_two) as data_file:
        data_two = json.load(data_file)

    ratings = Counter()
    for i in data_two:
        rating = int(i['yourrating'])
        if rating == 1:
            ratings[1] += 1
        elif rating == 2:
            ratings[2] += 1
        elif rating == 3:
            ratings[3] += 1
        elif rating == 4:
            ratings[4] += 1
        elif rating == 5:
            ratings[5] += 1
    ratings_count = sum(ratings.values())

    ones_2 = ratings[1] / ratings_count * 100
    twos_2 = ratings[2] / ratings_count * 100
    threes_2 = ratings[3] / ratings_count * 100
    fours_2 = ratings[4] / ratings_count * 100
    fives_2 = ratings[5] / ratings_count * 100

#creates graph
x = [1, 2, 3, 4, 5]
y = [ones, twos, threes, fours, fives]
y_2 = [ones_2, twos_2, threes_2, fours_2, fives_2]

plt.plot(x, y, label=user_one)
plt.plot(x, y_2, c='b', label=user_two)

plt.title('Comparative Netflix Ratings')
plt.ylabel('Percentage of Ratings')
plt.xlabel('Rating')
plt.legend(loc='upper right')
plt.xticks(np.arange(min(x), max(x)+1, 1.0))

plt.show()
```



And finally, we see that while I've done a pretty good job of maintaining a nearly normal distribution of ratings she is clearly inflating her ratings.

![png](/images/comparative_netflix_ratings.png)