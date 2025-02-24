---
title: "Assignment 1: Analyzing Sherlock Holmes Corpus"
author_profile: false
categories:
  - Blog
tags:
  - assignment
  - Post Formats
---
Written and researched by Ahmad Hafizh and Lucas Lin.

## Background

We wanted to do a ‘distant’ reading of Conan Doyle’s works. Sir Arthur Conan Doyle was a 19th-century British writer famous for the Sherlock Holmes series. Before gaining his fame as a series writer, he studied and worked as a physician. His knowledge of the medical world would then be reflected in his writings.

In this assignment, we are curious to see whether writing the Sherlock Holmes (SH) series would influence his later works. Particularly, to ask the question: ***Will we see changes in Doyle's writing style on his works after Sherlock Holmes?*** If so, we expect and hypothesize that many of the words and themes from SH series would be carried over to the next works. To satisfy this, we gathered nine different books in similar genres: adventure, crime, mystery, but all written by Doyle in different periods.

We took three books from the Sherlock Holmes series: A Study in Scarlet, its sequel, The Sign of the Four, and Adventures of Sherlock Holmes, a collection of short stories. Next, we gathered six books: three from before the writing of Holmes and three after.

### Material Selection

All materials we chose are arbitrarily chosen except for the time it was written and the genre, mystery. The Gully of Bluemansdyke, The Captain of the Polestar, and My Friend the Murderer all revolve around crime, human bodies, and supernatural stories.

A Study in Scarlet, The Sign of the Four, and Adventures of Sherlock Holmes provide us with more than enough resources to work as a benchmark. The White Company, Uncle Bernac, and Rodney Stones are works written post-Sherlock Holmes that talk about war, politics, and countries or kingdoms. These materials are publicly available and taken from Project Gutenberg.

### Our Process

We combine all books and separate them into three corpora. Books that were written before Sherlock Holmes would be called pre-Sherlock Holmes (pre-SH), the Sherlock Holmes Books (SHB), and post-Sherlock Holmes (post-SH). Then, we utilize Voyant Tools and RMarkdown in Posit.cloud to process these texts and output visualizations.


## Findings

## 1) Voyant Tools
 
## 2) RMarkdown
Our first analysis begins with a Word Cloud. Using this tool allows us to visualize our material generally. The most common words will pop-up and we can expect that words like Holmes or Sherlock should appear the most. 
![Word Cloud pre-SH ><](/assets/images/assignment1/img_wordcloud_preSH.png)
<br>This image is a word cloud from a corpus of books written before Sherlock Holmes. 
![Word Cloud SHBooks ><](/assets/images/assignment1/img_wordcloud_SHB.png)
<br>This image is a word cloud from a corpus of Sherlock Holmes books.
![Word Cloud post-SH ><](/assets/images/assignment1/img_wordcloud_postSH.png)
<br>This image is a word cloud from a corpus of books after Sherlock Holmes finished. 

### GGPlot Results

This time, we are using ggplot to reveal some more insights. The graph below shows the most recurring words in all selected Sherlock Holmes books. Based on the word cloud we generated previously, we expect the word ‘Holmes’ or 'Sherlock' to appear at the top. In this scenario, we sorted out the words so that only words that reoccur above 150 times would show up.
![ggplot Iteration](/assets/images/assignment1/ggplot_wordfreq.png)

**First Iteration**
Next, we compared the groups to get more insights. In the first iteration, we compared Sherlock Holmes books with pre-SH and post-SH. Our expectation is to observe words closer to the center line in Sherlock Holmes with post-SH compared to with pre-SH. 
![ggplot Iteration](/assets/images/assignment1/ggplot_first_iteration.png)

**Second Iteration**
In this graph, we modified the values of the jitter size, height, and width. We also adjusted the colors so that it differs from the first iteration. We observed that the change allowed for more distinct words to show up compared to the first iteration.
![ggplot Iteration](/assets/images/assignment1/ggplot_second_iteration.png)

**Third Iteration**
We decided to change things around this time by comparing pre-Sherlock Holmes books with the post and Sherlock Holmes series itself. The ggplot values are the same as the previous graph. Only the color is changed this time around.
![ggplot Iteration](/assets/images/assignment1/ggplot_third_iteration.png)

## 3) Conclusion
### # RStudio Conclusion
Our initial hypothesis suspects that writing Sherlock Holmes influences the works afterward. We expected that many words that did not appear in the books before Sherlock Holmes would reoccur after. This would be seen in the graph by having words closer to the center line between post-SH and Sherlock Holmes Books.

However, this did not turn out to be the case. Both methods of comparing Sherlock Holmes Books (SHB) with pre-Sherlock (pre-SH) and post-Sherlock (post-SH), against pre-Sherlock with post-Sherlock and Sherlock Holmes Books results in minor difference (refer to the graphs above). Using this tool could not give us a concrete answer to our question: does Sherlock Holmes influence Doyle’s work after?

What we do observe is that the themes regarding ‘adventure’ is relevant in all works. But, we conclude that Sherlock Holmes thickens this theme more, observable by how closer the word is in pre-SH to post-SH.

Another discovery we observed is the shift in themes between them. Sherlock Holmes Books share a common theme of human anatomy, medicine, and physician practices, judging by how words like ‘arm’, ‘bosom’, and ‘brain’ are relevant in these stories but not the ones after. We suspect that Doyle used these themes because of his physician background. By the end of his career, Doyle shifted the themes of his writing to a more political, historical, and war-focused apparent from the more distinctive use of words such as ‘battle’, ‘sword’, and ‘country’. These words could reflect the relentless conditions of Europe at that time (given how close it was to WW1 and WW2) 