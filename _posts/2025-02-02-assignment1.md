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

### Background
We conducted a distant reading of Sir Arthur Conan Doyle’s works to examine whether the Sherlock Holmes series influenced his later books. Doyle, best known for creating the legendary detective, was a 19th-century British writer whose background in medicine shaped his storytelling, particularly in forensic detail and logical reasoning.
This study investigates whether the themes, vocabulary, and stylistic choices of Sherlock Holmes carried over into Doyle’s later works. Using distant reading techniques, we analyzed a selection of Doyle’s books across three distinct periods—before, during, and after Sherlock Holmes. We employed Voyant Tools and Posit.cloud (RMarkdown) to track linguistic and thematic shifts across these periods.

### Hypothesis

>**We hypothesize that writing the Sherlock Holmes series influenced Doyle’s later works**. If so, his post-Holmes books should share notable similarities with the Holmes stories in vocabulary, themes, or narrative style. Given Holmes' popularity, we expected to see detective fiction elements carried over into Doyle's later works.

### Material Selection

All selected books were chosen based on their time of publication and genre, with a focus on mystery. While Doyle continued to write mystery and detective fiction beyond the Sherlock Holmes series, we focused on the following works to examine his stylistic and thematic evolution.

All materials were sourced from Project Gutenberg and categorized into three corpora:

<!-- Book table begin-->

|            Category            |                                                                      Title & Description                                                                      |                         Theme                        | Book ID |
|:------------------------------:|:-------------------------------------------------------------------------------------------------------------------------------------------------------------:|:----------------------------------------------------:|:-------:|
| Pre-Sherlock Holmes (pre-SH)   | The Gully of Bluemansdyke (1881)  - A collection of short stories exploring crime, morality, and human nature, often with dark or tragic themes.              |  Mystery \| Crime \| Supernatural \| Human Condition | #40848  |
|                                | “The Captain of the Polestar and Other Tales “(1883-1887)  - A mix of supernatural and adventure stories, featuring ghostly encounters and mysterious events. |  Mystery \| Supernatural \| Adventure                | #294    |
|                                | My friend the murderer (Late 19th c.) - A short story centered on crime and redemption, exploring themes of justice and guilt.                                |  Mystery \| Crime \| Human Condition                 |  #69260 |
| Sherlock Holmes:               | A Study in Scarlet (1887)  - The first Sherlock Holmes novel, introducing Holmes and Watson as they solve a murder linked to past events in America.          |  Mystery \| Detective                                | #244    |
|                                | The Sign of the Four (1890)  - A mystery involving a hidden treasure, betrayal, and an elaborate revenge plot.                                                |  Mystery \| Detective                                | #2097   |
|                                | Adventures of Sherlock Holmes (1892)  - A collection of short stories showcasing Holmes’ detective skills through various intriguing cases.                   |  Mystery \| Detective                                | #1661   |
| Post-Sherlock Holmes (post-SH) | The White Company (1891)  - A historical adventure novel set during the Hundred Years’ War, following a group of English archers.                             |  Historical \| War                                   |  #903   |
|                                | Uncle Bernac (1897)  -  A Napoleonic-era novel focused on espionage, war, and political intrigue.                                                             |  Mystery \| War (Napoleonic)                         | #10581  |
|                                | Rodney Stone (1896)  -  A historical novel blending themes of boxing, aristocracy, and naval warfare in 18th-century England.                                 |  Historical \| Boxing                                | #5148   |

<!-- Book table ends -->

>We refer to the bibliography [here](https://en.wikipedia.org/wiki/Arthur_Conan_Doyle_bibliography). The books analyzed in this study were sourced from Project Gutenberg, with their respective eBook ID numbers available for reference.

___  
### Our Process
A digital humanities workflow is composed of materials, processing, and visualization (Drucker 2). Our process involves selecting books from a large collection of Doyle’s works (Materials), inputting them into  Voyant Tools and Posit.cloud (RMarkdown) to be examined (Processing), and then displaying them as graphs in posts within a blog form (Visualization).
We organized the selected books into three corpora based on their publication period:
1. **`Pre-Sherlock Holmes (pre-SH):`** Works written before the introduction of Sherlock Holmes, reflecting Doyle’s early style and themes.
2. **`Sherlock Holmes Books (SHB):`** Novels and short stories from the Holmes series, serving as a benchmark for Doyle’s detective fiction.
3. **`Post-Sherlock Holmes (post-SH):`** Works written after Holmes, where we examine whether elements of detective fiction persist or if Doyle’s writing shifts towards new themes.
   
To analyze linguistic patterns, thematic shifts, and word frequency distributions, we used two primary tools:
**Voyant Tools:** We compiled all books within the same category into a single text file, creating three full-text documents: one for pre-SH, one for SHB, and one for post-SH. 
These combined texts were then uploaded into Voyant Tools, where we conducted word cloud analysis, frequency distributions, and general textual analysis to identify recurring terms and themes across different time periods. We also use **Posit.cloud** RMarkdown file that was introduced in the class:
- `Identifying the Most Distinctive Words Across Text Sets` – was used to compare vocabulary differences between pre-SH, SHB, and post-SH books. It was also used to generate word clouds. 
  
This method follows the ideas discussed in Rockwell and Sinclair’s "The Measured Words: How Computers Analyze Text", which explains how computational tools recognize patterns rather than interpret meaning. 
>While these tools helped us detect trends in Doyle’s writing, we applied human interpretation to refine our conclusions and gain a more nuanced understanding of the data.


___
## Findings

### 1) Voyant Tools
### General Information
![Voyant Words](/assets/images/assignment1/RMarkdown/Basic%20Info.png) 
The data reveals that Doyle’s writing evolved after Sherlock Holmes, with post-Holmes works having the highest word count and longer sentences, indicating a shift toward more descriptive storytelling. Sherlock Holmes books feature shorter sentences, reinforcing their fast-paced detective style. Despite these differences, Doyle’s vocabulary range remained stable, as seen in the consistent 6% type-to-word ratio. 

>The data does not strongly suggest that post-Holmes works retained the stylistic influence of Sherlock Holmes, implying a deliberate narrative shift in Doyle’s later writing.

<iframe style='width: 1112px; height: 673px;' src='https://voyant-tools.org/tool/ScatterPlot/?docId=81a2da64a1c005e22b2471173ef02741&docId=2749a81ed25292d87f0d823a8029fb76&docId=5ebae079c45f874a11df3273e9852b7a&limit=206&dimensions=2&label=docs&label=summary&view=topics&corpus=1d58c9ad21987f6fbb38a73090d4017c'></iframe>

The scatter plot above highlights a clear pattern in Doyle’s evolving writing style across different phases of his career:
>The close clustering of the Sherlock Holmes books (green) and the Pre-SH books (pink) suggests that while the detective stories had a distinct narrative focus, they still retained stylistic similarities with Doyle’s earlier works. This could indicate that his writing tendencies, such as sentence structure, word choice, or narrative flow, remained consistent even as he introduced the detective genre’s unique elements.

### Word Theme Analysis

#### Detective Related Terms
The Sherlock Holmes books (SHB) show a significantly higher use of detective-related terms compared to pre-SH books, with words like case, crime, mystery, investigation, clue, and solution appearing more frequently. `This indicates that Doyle refined and popularized the detective genre by making investigative elements central to the narrative.` In contrast, post-SH books show a noticeable decline in these terms, suggesting a shift away from detective fiction

![Voyant Theme Detective](/assets/images/assignment1/Bubbleline/detective%20words.png) 

#### Action Related Terms
Action and suspense-related terms were minimal in Doyle’s pre-Holmes works, moderately present in the Sherlock Holmes stories, and significantly increased in post-Holmes books. `While Holmes’ narratives emphasized deduction over action, Doyle’s later works leaned toward adventure-driven storytelling, incorporating more frequent mentions of fight, thrill, and chase.` This shift suggests a departure from pure detective fiction, aligning with the rise of pulp fiction and early thriller genres.

![Voyant Theme Detective](/assets/images/assignment1/Bubbleline/Action%20&%20Suspense%20Terms%20.png) 

##### Psychological Terms 

![Voyant Theme Detective](/assets/images/assignment1/Bubbleline/Psychological%20Terms.png) 

Sherlock Holmes introduced psychological themes such as perception, deception, and manipulation, making them more prominent than in Doyle’s pre-Holmes works. Post-Holmes books expanded even further on these elements, emphasizing psychological complexity. This suggests that while Holmes played a crucial role in shaping psychological themes in detective fiction, later works evolved beyond imitation, deepening the exploration of human psychology.

#### Character and Role Terms

![Voyant Theme Detective](/assets/images/assignment1/Graphs/%20Character%20&%20Role%20Terms.png) 

The bar graph illustrates the evolution of character and role-related terms in Doyle’s works. During the Sherlock Holmes era, terms like "inspector," "detective," and "criminal" rise significantly, reflecting a strong focus on investigation. Pre-Holmes books feature "inspector" and "agent" but with less emphasis on detectives. Post-Holmes, detective-related terms decline as "officer" becomes more prominent, marking a shift from detective-driven narratives to broader authority figures. This suggests that while Holmes reinforced Doyle’s engagement with crime and justice, his later works shifted toward legal and societal themes over individual investigations.


## 2) RMarkdown
Our first analysis begins with a Word Cloud. Using this tool allows us to visualize our material generally. The most common words will pop-up and we can expect that words like Holmes or Sherlock should appear the most. 
![Word Cloud pre-SH ><](/assets/images/assignment1/img_wordcloud_preSH.png) <br>
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

## 3) Discussion & Conclusion
Our initial hypothesis was that writing Sherlock Holmes influenced Doyle’s later works. We expected words that were absent before Sherlock Holmes to recur afterward, appearing closer to the center line between post-Holmes and Sherlock Holmes books in our analysis. However, the data did not support this assumption. Comparing Sherlock Holmes books (SHB) with both pre-Sherlock (pre-SH) and post-Sherlock (post-SH) works showed only minor differences. Thus, this computational approach could not definitively answer whether Sherlock Holmes influenced Doyle’s later writing.

Unlike close reading, which provides specific insights, distant reading offers broader patterns that require further interpretation (Drucker 115).Our findings reveal that the theme of ‘adventure’ is present in all of Doyle’s works, though Sherlock Holmes deepens this theme, as evidenced by its closer alignment between pre-SH and post-SH texts. Another significant discovery is the thematic shift across different periods. Sherlock Holmes books prominently feature human anatomy, medicine, and physician-related terms—such as ‘arm,’ ‘bosom,’ and ‘brain’ which are likely influenced by Doyle’s medical background. By the end of his career, Doyle’s works shifted toward political, historical, and war-focused themes, seen in the increasing use of words like ‘battle,’ ‘sword,’ and ‘country.’ This shift may reflect the political climate of Europe, given its proximity to WWI and WWII.

Utlizing both Voyant Tools and RStudio, our analysis shows that while Sherlock Holmes was a pivotal phase in Doyle’s career, it did not permanently alter his writing style. Before Holmes, his works explored crime, morality, and the supernatural. During the Holmes era, his writing became sharper and centered on investigation and logical reasoning. However, after Holmes, Doyle moved away from detective fiction, favoring historical adventure, war, and politics.

>All in all, Sherlock Holmes refined the detective genre, but it was a distinct phase rather than a defining influence on Doyle’s later works. His post-Holmes books returned to themes more in line with his early storytelling—adventure, history, and human psychology—rather than investigative crime fiction. Through computational analysis and human interpretation, we conclude that while Holmes left a mark on the mystery genre, Doyle himself moved on.
