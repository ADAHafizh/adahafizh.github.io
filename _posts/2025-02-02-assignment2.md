---
title: "Assignment 2: Mapping Zanzibar 1909"
categories:
  - Blog
tags:
  - assignment
  - Post Formats
---
## Background
### Source Material
For this assignment, we are using the Zanzibar Gazette Year 1909. The year was chosen considering metadata quality (the ability to search texts inside) and visibility (how good the visuals are). Our next consideration is the tidiness of the data. The year 1909 onwards provide better layout and clarity on the information stored compared to previous years. We also would like to avoid the years between 1914 - 1918 as it was the period of World War I, and we expect lower amounts of data in the Gazette during these years.

In this collection, we scrambled through the tables within. As far as we observed, there are tables regarding mail, meteorological reports, custom and principal item reports, ship sailings, and shipping reports. Zanzibar Gazette’s shipping report caught our attention for two reasons: a) compared to other tables, shipping reports were more consistent in terms of layout because it is legible enough for us, and presumably for our machine to read. b) we would like to automate our processes as best as possible so that we could allocate our time for in-depth analysis and visualization of our map.

### Competition Between Machines
Initially, we used the free version of ChatGPT-4 as our primary machine to recognize the text. However, we soon encountered a limit to the processing demands of around 5 prompts and 20 rows of data analyzed. Because of this limit, we decided to change our program to use Google’s [Gemini](https://gemini.google.com/app) and [DeepSeek](https://www.deepseek.com/).

> For both programs, we used the same initial prompt (or similar):
> **“Please generate me a table and .csv file for the image shown here.”**

This prompt allows us to gain two things from the generation. First, by displaying the .csv file in a table, we can immediately see the result that the AI has generated. This display is important as it will provide us with a quick spot if the AI missed or falsely recognized the text. Second, the .csv file helps us import the data into [Google Sheets](https://sheets.google.com/). We also compared both DeepSeek and Gemini results to see whether they would generate different results. In later parts of our article, we will discuss the pros and cons of both tools.

But this decision could not last for very long as Gemini did not have .csv reading capabilities. Whenever we tried to upload .csv files, the tool would not read the file. Luckily, we found out that DeepSeek was able to both perform OCR and examine .csv files. Thus, in the end, we decided to rely on our research by using DeepSeek.

After working on our assignment with both Google’s Gemini and DeepSeek, here are some of our thoughts:
1.  **Gemini**
- The tool lacked .csv file reading capabilities. Since our work relied heavily on this file type, we felt that we were limited by the tool.
-  For OCR, Gemini does not correct itself and instead chooses to give whatever it recognizes. In other words, if the outcome produced by Gemini contained a mistake, it would likely persist.
2. **DeepSeek**
- In comparison, DeepSeek can clean up data. As an example, DeepSeek understands dittos in the table and assumes that it should follow the preceding table value. There are also several cleanups that the tool performed which we will showcase later.
- Moreover, DeepSeek is capable of reading .csv files. This process helped us tremendously as it was able to refer to our data structure; hence, when new OCRs are performed, the output was easily mergeable with ours.

> **All in all, DeepSeek takes the crown as it was able to perform tasks and deliver satisfactory results for our research. Tthe tool gave us unique insights based on the table, a task that would have taken a long time to examine had we done it manually, reading row by row.**

## Modeling
### Processing the Report
The following is a detailed explanation of our processes. We extracted shipping information from the Zanzibar Gazette 1909 by first screenshotting each page. Then, we fed this image to Google Gemini. The following are the prompts (bold texts) with their respective results that Gemini gave us. Then, we exported this .csv data into Google Sheets and created a table by splitting columns. From there, we decided to alter some of the header and data that we deem important to ‘clean’ further.

> **Hello! Can you please generate me a table and .csv based on the image shown?**
Absolutely! Let's break down the information in the image and create a table and a CSV representation.

| ![Prompt 1.png](/assets/images/assignment2/prompt_1.png)  |
|---|
| ![Prompt 1.png](/assets/images/assignment2/prompt_1(2).png)  |

There are several changes that we made before visualizing our data:
1.  Changing cargo type into ship type
- We examined that based on the two tables, we can classify the ships into two categories: a cargo ship and a warship (Man-O’-War). Cargo Type, we deem, is unnecessary for our research and would not provide beneficial information. Instead, knowing what type came during a specific week of the month (that is, cargo ships or warships) makes our data much more interesting.
2. Still in Harbour
- During our examination, we encountered the phrase *Still in harbour* several times. It usually appears in a ship’s *Bound To* column. We assume that this phrase signifies that the ship has yet to depart from its original harbor. We decided that instead of inputting Still in Harbour, having the original harbor’s name would be better as later on, in our visualization map, no lines are formed since the ship’s location did not change.
3. Spelling Correction
- We noticed that there are locations which does not exist or would not work when we tried to use the GeoCode extension on them. For example, German Coast does not refer to an actual location. South also appeared several times. To ensure our geocoding works, we decided to change these names to Germany and (we presume) South Africa.
4. Due to the image quality, Gemini made mistakes on the recognized characters. Some dates, for example, would refer to 1900 instead of 1909. Partly because of its similarities. Some names, such as Wami, were mistaken as Wani. We compared the table and did manual edits to these data ourselves.
### Mapping our Data

## Data Correction
### A Major Overlook
During three-quarters of the process, we noticed a major oversight from our side when we tried to visualize our data. We took ‘snippets’ of the shipping report by cutting half of the page. However, upon closer inspection, juxtaposing the reports of 16th March 1909 with others, we noticed that all shipping reports of Zanzibar Gazette 1909 occupy full pages.  This means that the actual report is not only limited to the cargo ships but also includes warships (categorized as Man-O-War) and smaller traditional vessels (classified as Dhows). In exchange, our data visualization, which was previously limited to cargo ships, was now expanded to include other types of ships.
With this new information in mind, we have decided to include warships in our shipping report table. However, because ‘Dhows Arrived’ and ‘Dhows Departed’ data, we decided not to include it in the main table and instead opted to create a separate table and represent it using bar graphs.
### Nudging the Tool
After having worked on over a hundred rows, fatigue started to envelop our team. We realized that manually editing the rows and columns was not a viable solution. Instead, since we already curated these rows, we thought of something:

>***“What if we feed the machine our edited tabular data and ask them to do OCR and generate the output based on our table structure?”***

At this point, we learned that Gemini did not support .csv files. Luckily, DeepSeek does. The following conversation is the prompts that we use to generate over 100 rows for our table by using DeepSeek.

| Prompt                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           | Output                                                                                                                                             |
|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------|
| Uploaded 1909_ShippingReport.csv (our base file) Okay. I have attached a file here. Please examine the file and take note of the headers and the contents stored within.                                                                                                                                                                                                                                                                                                                                                         | DeepSeek examines the file.  Let me know if you’d like to explore specific aspects (e.g., filtering by nationality, time ranges, or missing data)! |
| Uploaded a screenshot of the Zanzibar Gazette Shipping Reports 1 June 1909 Now, examine the 1909_ShippingReport.csv file I have provided. If you still remember and examined correctly, you should notice that the tabular data image I have provided you contains data structured similarly to the .csv file I provided. Can you merge the .csv file I just provided with the ones you created? Ignore the longitude (from), latitude (from), longitude (destination), and latitude (destination) columns and leave them empty. | ![Prompt 2.png](/assets/images/assignment2/prompt_2.png)                                                                                           |
| Remember the steps that you have done previously. Here is a new image similar to the ones I gave before. Extract the textual information and adjust the data so that it fits the 1909_ShippingReport.csv structure while ignoring longitude (from), latitude (from), longitude (destination), and latitude (destination) columns and leave them empty.                                                                                                                                                                           | ![Prompt 3.png](/assets/images/assignment2/prompt_3.png)                                                                                           |


## Visualization
### Fantastic Dhows and Where to Find Them
Initially, we tried using Google Sheets to represent our analysis on Dhows. However, we encountered numerous problems regarding Timeline Graphs, and the outcome did not display the data like we expected. Instead, we used an online tool called [CSV Plots](https://www.csvplot.com/) to map our data in a line graph. 
![Dhows Sailed](/assets/images/assignment2/Graph_Line_Dhows_Sail.png)

Dhows Arrived

![Dhows Arrived](/assets/images/assignment2/Graph_Line_Dhows_Arrive.png)
## Discussions
Zanzibar was a major maritime trade hub in East Africa. In 1909, it was under British colonial rule but had strong connections to Arabian traders, particularly from Oman. The high number of Zanzibar/British dhows indicates local dominance in maritime activity. 
-   Zanzibar remained a significant maritime trade hub under British influence in 1909.
-   Zanzibar/British dhows were the most active, indicating local trade control.
-   Seasonal fluctuations might suggest dependency on weather patterns during the months.
-   Arabian and German traders had moderate involvement, while French traders played a minor role.
## Conclusion