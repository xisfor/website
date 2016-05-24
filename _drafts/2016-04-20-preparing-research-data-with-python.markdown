---
layout: post
title: Preparing linguistic research data with Python
date: 2016-04-20
categories: python data
---

There is a battle raging amongst academics; should you use R or Python? As a developer in the trenches, I'm asked which is better. Of course, it really depends on your dataset. But as a generalist, I'd go Python for its everyday usability, so I'm going to talk about that.

## Preparation

The first task of any data processing is preparing your data. Your initial dataset can come in many forms, but they generally fall into these broad categories:

 - Data you've collected, probably in a spreadsheet.
 - Files collected, possibly from a 3rd party.
 - Web pages.

Don't try to achieve the all encompassing solution from the start. You want to get yourself to a point where you can play with a few ideas.

Probably the best tool for hacking around with data manipulation and prototyping is a spreadsheet. This allows for quick sorting, filtering and interrogation, giving you to some quick wins.

So first up, aim to get data into a spreadsheet. After that, you can look at graphs, statistical analysis, etc.

By far the easiest dataset is one you've collected and entered into a spreadsheet as you were collecting it.

3rd party files are a real pain. Finding rhyme or reason as to why they are the way they are is often half the battle. To be able to programmatically collect and filter the contents, you need to:

 - Assess the file types and identify if you can you extract the data.
 - Be able to drill down in to their compositional detail.
 - Figure out how to create a standardised output.

Don't try to deal with the complete set in one go. Start with a sample file. Is it a plain text file? An HTML document? a PDF? Is it typical of the dataset?

Dealing with a plain text file is something you can easily examine programmatically.

HTML files, though plain text in their own way, tend work best when parsed by a library like [Beautiful Soup](https://www.crummy.com/software/BeautifulSoup/).

PDFs would probably want to use an external application, like [pdftotext](https://en.wikipedia.org/wiki/Pdftotext), to preprocess.

Office files, like Word, need an unpackaging process before you can process them. See this [article on reading docs in python](http://virantha.com/2013/08/16/reading-and-writing-microsoft-word-docx-files-with-python/). In all, I'd say avoid storing data in Word/Office documents.


## Basic processing

In computer science, we consider language to be made up of strings. A sequence of characters. What you're looking to do is read a file, find the required strings, and write them out to a file. We would usually write out the steps we're going to need to take first as pseudocode:

{% highlight bash %}
  open web page
    find all the list items
      for each list item with string "x is for"
        write string to csv file
{% endhighlight %}

We would then, line by line, turn that into code:

{% highlight python %}
# used to open web pages
import urllib2

# used to read web pages
from bs4 import BeautifulSoup

# get a csv file ready to write in
csv_file = open('output.csv', 'w')

# open web page
page = urllib2.urlopen('http://xisfor.tech/blog')

# make web page readable
soup = BeautifulSoup(page, "html.parser")

# find all the list items
list_items = soup.body.find_all('li')

# for each list item
for list_item in list_items:

  # does string contain what we're looking for?
  if "x is for" in list_item:

    # write string to our csv file
    csv_file.write(list_item)

# close the file to finish
csv_file.close()
{% endhighlight %}

Of course, there ended up being more than our original pseudocode, but it was enough to get us started. As I said, don't target the final solution, just work through what you know at the time, research each part as you go and develop and build.

This should be enough to get you to CSV file, which you can then import into a spreadsheet for interrogation.

_This is intended to be the first in a series of article on working with linguistic datasets. <a href="/contact">Get in contact</a> if you want me to provide further information that may help you._
