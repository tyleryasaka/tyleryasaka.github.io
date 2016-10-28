---
layout: post
title:  "Drowning in the Big Data Lake"
date:   2016-10-27
---

Apparently, "data lakes" are all the rage these days among big data peoples. Here I take a brief look at what they are, when to use them, and things to consider about them. (Disclaimer: I have no experience using data lakes at the time of writing.)

# What they are

(This is a rough overview. See the [sources](#sources) at the end of this post if you to learn more about the specifics.)

Data lakes are places to store large quantities of data in its "natural" state. This is in contrast to typical data storage mechanisms (like databases) which require data to be input in a very specific format. In a SQL database, for example, each record in a table is required to have precisely the same number of columns as all the other records in that table. Even in a "nosql" database like MongoDB, where each document can have a completely different set of fields, the data is still required to be in a very strict JSON format.

Contrast this with data lakes, where data is merely dumped in as it is, with little or no attempt to convert it to any sort of format to be usable in the future. This is done to preserve the data in a raw format, so that absolutely no information is lost when it is saved. The idea is that the data can be converted to a more useful format at a later phase. 

# When to use them

Data lakes are great for "big data" operations that generate large amounts of potentially interesting data. The data might be in various formats  (JSON, plain text, jpg, etc.), and it would be imposible to know how the data might be used in the future, much less how to convert it to a useful format. By storing it in this "lake", the task of data organization can be postponed to a later phase.

# To be useful, the data must (eventually) become readable

Data is only useful when it is in a readable format. Storing data in a big "lake" is fine and dandy, but it is important to keep in mind that the data is not going to magically organize itself and spit out the answers we want to hear (unless that answer is ["Forty-two"](https://duckduckgo.com/?q=The+Answer+to+the+Ultimate+Question+of+Life%2C+the+Universe%2C+and+Everything&t=h_&ia=answer)). This is work that will either have to be done by a human or by an automated process of some sort. The more disordered the data, the more work will be involved in understanding it (and the more intelligent an automated process will need to be).

# Don't forget security

The general idea of a data lake raises some security concerns. If you are indiscriminately dumping data by the terabytes into a single free-for-all repository, you want to make sure sensitive information like credit card numbers and passwords don't get anywhere near it. If confidential data is accidentally dripped into the lake, I imagine it would be very difficult to "decontaminate". The issue becomes even more complex when you take into account permission hierarchies. There might be a few superusers with complete access to all data; there might be some people with "dump" (write) acccess; and there might be some people with permissions to read only *some* of the data. If the data is supposed to be raw and untampered, how do we enforce these permissions? (Rhetorical question.)

# TODO

- Investigate actual implementations of data lakes such as hadoop
- Think about how data lakes can be combined with data analysis techniques such as unsupervised machine learning as a way to explore the data

### Sources
- <http://www.forbes.com/sites/ciocentral/2011/07/21/big-data-requires-a-big-new-architecture/#30c78a4e1d75>
- <http://www.pwc.com/us/en/technology-forecast/2014/cloud-computing/assets/pdf/pwc-technology-forecast-data-lakes.pdf>
- <http://www.gartner.com/newsroom/id/2809117>
