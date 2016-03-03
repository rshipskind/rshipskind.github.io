---
layout: post
title:  "The Trump Availability Cascade"
date: 2016-03-02-trump-availability-cascade
categories: post
excerpt_separator: <!--more-->
permalink: trump-availability-cascade
---

Over the past 9 months the political world has slowly brought itself around to the idea that Donald Trump can pretty comfortably be referred to as the presumptive Republican nominee. What seemed at first to be a joke to many has blossomed now, a day after Super Tuesday to be the most likely outcome of the primary (As of this moment [betting markets have him at 1:4 odds](http://www.oddschecker.com/politics/us-politics/us-presidential-election-2016/republican-candidate) of securing the nomination). So how did we get here?<!--more-->

One key point in the evolution of the Trump candidacy in my mind is the availability cascade - the self-reinforcing process of collective belief formation by which the expression of an idea makes its plausibility increase. The more we hear about Trump, the more we take him to be a legitimate candidate.

Trumps national TV mentions correlate very well with Google searches for Trump.

![Trump TV mentions vs Google searches](/assets/trump_mentions_vs_searches.png)

National TV mentions correlate very strongly with searches (r = .873). But its still unclear how well searches map to vote preference.

Using [analysis by the GDELT Project with data from the Internet Archive Television News Archive](http://television.gdeltproject.org/cgi-bin/iatv_campaign2016/iatv_campaign2016?filter_candidate=DONALD_TRUMP&filter_network=NATIONAL&filter_timespan=SINCETRUMP&filter_displayas=RAW) and [polling data from RealClearPolitics](http://www.realclearpolitics.com/epolls/2016/president/us/2016_republican_presidential_nomination-3823.html) looking at Trump's polling percentage against the number of mentions he's received on national television during the time the poll was conducted.

![Trump Poll Results vs. TV mentions](/assets/trump_mentions_vs_polling.png)

For every additional thousand times Trump was mentioned on national television during the time a poll was in the field he performed 1.35% better in that poll (r^2 = .193).

[Check the data and code](https://github.com/rshipskind/trump_availability_cascade)
