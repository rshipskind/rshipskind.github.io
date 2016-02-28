---
layout: post
title:  "Comparative Netflix Ratings"
date:   2016-02-23
categories: blog
---

I often find myself rating a Netflix show after watching it with my wife. Unfortunately, I find myself frequently giving harsher ratings than she does. So, one weekend while she was out of town, I decided to empirically prove that she was systemically inflating her ratings. Luckily, exporting our ratings was made simple with the help of [Flix Plus](https://github.com/jaredsohn/flix_plus).

Because I figured I might have some friends who were interested in seeing how their ratings compared once I posted the graph to Facebook I included an option to pass on the second json file in order to graph just one set of ratings without throwing an error.

```python
# imports json data
json_one = input("Filepath to first account JSON: ")
user_one = input("User one: ")
json_two = input("Filepath to second account JSON, or 'pass': ")
if json_two != 'pass':
    user_two = input("User two: ")
```
Once the json files were downloaded and opened it was a simple matter to parse the file to count how many of each rating the user had given with collections.Counter.

```python
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
```
If a second json file is passed the same process is repeated. Then, a quick call to matplotlib to plot the data and some time playing around with settings to make it look nice.

```python
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

![Comparative Netflix Ratings Graph](/images/comparative_netflix_ratings.png){: .center-image }

To which she understandably responded, "Why would I even want normally distributed ratings?"

Touché.

[Check the code](https://github.com/rshipskind/netflix_ratings/blob/master/netflix_ratings.ipynb)
