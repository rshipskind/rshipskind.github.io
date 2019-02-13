---
layout: post
title:  "What's my win number? An analysis of Multimember District vote shares"
date:   2019-02-13  
categories: post
excerpt_separator: <!--more-->
permalink: mmd-vote-share
---

It's easy enough to determine what percentage of votes you need to win an election when only one candidate will be elected. But what happens when the top 2 vote getters both win a seat? I dug into the results for Vermont State House races in 2014, 2016 and 2018 to determine what percentage of the votes you'll need to win a seat (probably). <!--more-->

In a race in which 2 candidates are running for 1 seat, you need 50%+1 vote to guarantee victory. Likewise, when 4 candidates run for 2 seats you need 33%+1 to guarantee a seat. The first stumbling block for a candidate in this multimember seat, however, arises when you realize, that with each voter casting 2 votes, if 50% of the district casts 1 of their votes for you, that only nets you 25% of the total votes cast, not the 33% of votes necessary to guarantee your election. In fact, because each voter can only vote for you once, you would need closer to 67% of the electorate to cast one of their votes for you to guaranteee your election - a much higher bar than the 50% needed in a single member district.

Looking at Vermont State House elections in 2014, 2016 and 2018 in multimember districts, I've created the following graph for how likely a candidate was to win a seat based on their vote share below.

![MMD Vote Share graph](/assets/MMD_winning_vote_share_results.png){: .center-image }

The minimum winning vote share was 14.2%, while the maximum losing vote share was 31.6%

While getting 50% of voters to support you (25% vote share) is usually sufficent to win your seat in a 2 member district, this is not always the case, with a 25% vote share being a winning total about 60% of the time. Meanwhile a 24.1% vote share wins a seat 50% of the time. If you want a vote share that wins a seat 95% of the time, you'll need to secure 30.8% of the votes which is the support of 61.6% of the voters, and if you're willing to live dangerously and pick a vote share that wins you that seat 9 times out of 10, you'll be aiming to secure a vote from 58.2% of the voters to secure 29.1% of the vote.

[Check the code](https://github.com/rshipskind/mmd_win_number)
[and data, courtesy of the VT SoS Elections Division](http://vtelectionarchive.sec.state.vt.us/elections/search/year_from:2014/year_to:2018/office_id:8/stage:General)