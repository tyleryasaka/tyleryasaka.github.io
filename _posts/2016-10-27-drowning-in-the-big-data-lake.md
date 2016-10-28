---
layout: post
title:  "Drowning in the Big Data Lake"
date:   2016-10-27
---

Apparently, "data lakes" are all the rage these days among big data peoples. Here I take a brief look at what they are, when to use them, and things to consider about them.

# What they are

Data lakes are places to store large quantities of data in their "natural" state. This is in contrast to typical data storage mechanisms (like databases) which require data to be input in a very specific format. In a SQL database, for example, each record in a table is required to have precisely the same number of columns as all the other records in that table. Even in a "nosql" database like MongoDB, where each document can have a completely different set of fields, the data is still required to be in a very strict JSON format.

Contrast this with data lakes, where data is merely dumped in as it is, with no attempt to convert it to any sort of format to be usable in the future. This is done to preserve the data in a raw format, so that absolutely no information is lost when it is saved. The idea is that the data can be converted to a more useful format at a later phase.

# When to use them

Data lakes are great for "big data" operations that generate large amounts of potentially interesting data. The data might be in various formats  (JSON, plain text, jpg, etc.), and it would be imposible to know how the data might be used in the future, much less how to convert it to a useful format. By storing it in this "lake", the task of data formatting can be postponed to a later phase.

# To be useful, all data must be ordered eventually

Data is only useful when it is in a readable, uniform format. Storing data in a "lake" is fine and dandy, but it is important to keep in mind that just because we have kicked the can of data organization down the road, it doesn't mean we can avoid the inevitable step of deriving meaning from the data. This is work that will either have to be done by a human or by an automated process of some sort. The more disordered the data, the more work will be involved in understanding it (and the more intelligent an automated process will need to be).

# Don't forget security

The general idea of a data lake sounds like a security breach waiting to happen. Indiscriminately dumping data by the terabytes into a single free-for-all repository is just asking for the wrong data to get in the wrong hands. I personally know nothing about actual implementations of data lakes such as Hadoop (though I would like to try one out sometime), so I can't speak to the security of those systems. I am just wary of potential vulnerabilities that could arise from misuse.

# TODO

- Investigate actual implementations of data lakes such as hadoop
- Think about the possibly combining data lakes with data analysis techniques such as unsupervised machine learning to find meaning in otherwise meaningless data

### Sources
- <http://www.forbes.com/sites/ciocentral/2011/07/21/big-data-requires-a-big-new-architecture/#30c78a4e1d75>
- <http://www.pwc.com/us/en/technology-forecast/2014/cloud-computing/assets/pdf/pwc-technology-forecast-data-lakes.pdf>
- <http://www.gartner.com/newsroom/id/2809117>
