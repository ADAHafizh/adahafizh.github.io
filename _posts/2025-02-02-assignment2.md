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

In this collection, we scrambled through the tables within. As far as we observed, there are tables regarding mail, meteorological reports, custom and principal item reports, ship sailings, and shipping reports. Among these, the Shipping Reports caught our attention for two main reasons: 
1. They featured a relatively consistent layout and clear quality, making them easier for us and for the machines to process. 
2. Their ease of transcription allowed us to focus on automating the data extraction process and investing more time in in-depth analysis and visualization.


### Competition Between Machines

One cornerstone that Klein touched upon is the idea that ‘*the bigger AI model does not mean it is better.*' Their research studies indicate that simply increasing the amount of data, model complexity, or computational power does not necessarily improve the accuracy of AI outputs. For humanities researchers, this suggests that striving for a single, all-encompassing form of artificial intelligence is a complex and problematic goal, highlighting the limitations of such an approach.

Initially, we used the free version of ChatGPT-4 as our primary machine to recognize the text. However, we soon encountered a limit to the processing demands of around 5 prompts and 20 rows of data analyzed. Because of this limit, we decided to change our program to use Google’s [Gemini](https://gemini.google.com/app) and [DeepSeek](https://www.deepseek.com/).

> Initially, we used this prompt for Google Gemini:
> **“*Please generate me a table and .csv file for the image shown here.*”**

This prompt allows us to gain two things from the generated outcome. First, by displaying the .csv file in a table, we can immediately see the result that the AI has generated. This display is important as it will provide us with a quick spot if the AI missed or falsely recognized the text. Second, the .csv file helps us import the data into [Google Sheets](https://sheets.google.com/). We also compared both DeepSeek and Gemini results to see whether they would generate different results. In later parts of our article, we will discuss the pros and cons of both tools.

After working on our assignment with both Google’s Gemini and DeepSeek, here are some of our thoughts:
1.  **Gemini**
- The tool lacked .csv file reading capabilities. Since our work relied heavily on this file type, we felt that we were limited by the tool.
-  For OCR, Gemini does not correct itself and instead chooses to give whatever it recognizes. In other words, if the outcome produced by Gemini contained a mistake, it would likely persist.
1. **DeepSeek**
- In comparison, DeepSeek can clean up data. As an example, DeepSeek understands dittos in the table and assumes that it should follow the preceding table value. There are also several cleanups that the tool performed which we will showcase later.
- Additionally, DeepSeek can read .csv files , which allowed it to reference our existing data structure. This feature proved especially useful, as new OCR outputs could be seamlessly merged with our dataset.

> All in all, DeepSeek takes the crown as it was able to perform tasks and deliver satisfactory results for our research. Perhaps it was trained under similar data to recognize better than Gemini. Moreover, the tool gave us unique insights based on the table, a task that would have taken a long time to examine had we done it manually, reading row by row.
>

## Modeling
### Processing the Report
The following is a detailed explanation of our processes. We extracted shipping information from the Zanzibar Gazette 1909 by first screenshotting each page. Then, we fed this image to Google Gemini. Next are the prompts (bold texts) with their respective results that Gemini gave us. Then, we exported this .csv data into Google Sheets and created a table by splitting columns. From there, we decided to alter some of the header and data that we deem important to ‘clean’ further manually. 

> **Hello! Can you please generate me a table and .csv based on the image shown?**
Absolutely! Let's break down the information in the image and create a table and a CSV representation.

| ![Prompt 1.png](/assets/images/assignment2/prompt_1.png)  |
|---|
| ![Prompt 1.png](/assets/images/assignment2/prompt_1(2).png)  |

There are several changes that we made before visualizing our data:
1.  **Changing cargo type into ship type**
- We examined that based on the two tables, we can classify the ships into two categories: a cargo ship and a warship (Man-O’-War). Cargo Type, we deem, is unnecessary for our research and would not provide beneficial information. Instead, knowing what type came during a specific week of the month (that is, cargo ships or warships) makes our data much more interesting.
2. **Still in Harbour**
- During our examination, we encountered the phrase *Still in harbour* several times. It usually appears in a ship’s *Bound To* column. We assume that this phrase signifies that the ship has yet to depart from its original harbor. We decided that instead of inputting Still in Harbour, having the original harbor’s name would be better as later on, in our visualization map, no lines are formed since the ship’s location did not change.
3.  **Geographic Data Verification Process**
 - The geocoding phase revealed several categories of location-related challenges that demanded tailored solutions. For completely unrecognizable place names like "German Coast," we conducted archival research to determine appropriate modern equivalents (in this case, "Germany"). Vague directional terms such as "South" were interpreted through careful analysis of shipping routes and contextual clues, typically defaulting to "South Africa" when no clearer alternative emerged. We addressed variable spellings (e.g., "Daressalaam"/"Dar es Salaam") by creating and applying a standardized names reference list. Particularly challenging were obsolete terms like "Tania" and "Gaulle ato Dobouti," which required consultation of historical shipping records and colonial-era documents before we could confidently map them to contemporary equivalents.
    

4.  **Text Recognition and Formatting Corrections**
- The suboptimal quality of source images necessitated an extensive manual review process for the OCR-generated data. Our team performed side-by-side comparisons of extracted data with original newspaper scans, developing a comprehensive list of common error patterns (e.g., "1900" vs "1909", "Wami" vs "Wani") to guide systematic corrections. We established rigorous formatting standards for ship prefixes (S.S., C.S.), ensuring consistent spacing, punctuation, and proper column assignment through verification against known shipping registries. Company naming conventions were normalized through the implementation of strict formatting rules governing initial spacing (D.O.A.L. vs D. O. A. L.), capitalization standards (Co. vs co.), and punctuation guidelines for ampersands and abbreviations. Every data point underwent double verification to ensure accuracy, particularly for numerical values where OCR frequently misidentified similar-looking digits in low-quality scans.
    

5.  **Temporal Data Preparation**
- Preparing the date data for Kepler visualization demanded careful precision. We developed a strict standardization process that first reconstructed incomplete dates by analyzing contextual clues from adjacent entries and the newspaper's publication rhythm. Each timestamp was then reformatted to include both date and time components, with empty time values automatically set to 00:00:00. This involved manually processing the entire date column to enforce uniform formatting - every entry was verified to follow the exact "1909-MM-DD 00:00:00" structure, ensuring compatibility with Kepler's visualization requirements. Special attention was given to correcting OCR errors in dates while maintaining historical accuracy throughout the dataset.
    

6.  **Ship Prefix Standardization Process**
- The inconsistent formatting of ship prefixes (S.S. for steamship, C.S. for cable ship) required extensive manual correction, as they frequently appeared in wrong columns, were omitted entirely, or contained irregular spacing/punctuation (e.g., "S .S.", "S.S ."). We systematically audited each entry, cross-referenced historical registers to verify proper prefixes, and standardized all variations to "S.S." or "C.S." format.

## Data Correction
### A Major Overlook
Three-quarters into the process, a significant oversight came to light when we attempted to visualize our data. We had been taking 'snippets' of the shipping reports by cropping only half of the page. However, upon a closer comparison—specifically juxtaposing the 16th March 1909 report with others, we realized that every Zanzibar Gazette shipping report from 1909 spans an entire page. 

This discovery revealed that the reports were not limited to cargo ships but also included warships (categorized as Man-O-War) and smaller, traditional vessels (classified as Dhows). Consequently, what was once a visualization focused solely on cargo ships was expanded to encompass a broader range of maritime activity. 

With this new insight, we decided to incorporate warships into our primary shipping report table. However, since the Dhows Arrived and Dhows Sailed  data followed a different structure, we chose not to integrate them into the main table. Instead, we created a separate table and visualized the dhow data using bar graphs. 

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
### Mapping Zanzibar Shipping Report 1909
We created an interactive map by importing our standardized dataset into Kepler, structuring it with three primary visualization layers: 
1. **Origin Points:** Translucent circles mark each departure location—blue for cargo ships and red for warships—plotted using their departure coordinates. 
2. **Destination Markers:** Uniform yellow dots represent the “Bound To” locations. 3. Trajectories: Dynamic arrows connect origin and destination points, color-coded by vessel nationality (British = red, German = green, French = blue, etc.). 

For clarity, origin labels are styled in blue, and destination tags in yellow. We added a temporal dimension using an animated timeline (set to 2x playback speed), which renders routes sequentially based on rigorously formatted arrival dates (DD-MM-YYYY 00:00:00). This multi-layered visualization communicates three key narratives: (a) geographic movement patterns via the point-to-point connection system, (b) national fleet distributions through chromatic encoding, and (c) historical sequencing via the time-based animation.


| ![Kepler Map](/assets/images/assignment2/Map.gif)  |
|---|

### Fantastic Dhows and Where to Find Them
Initially, we tried using Google Sheets to represent our analysis on Dhows. However, we encountered numerous problems regarding Timeline Graphs, and the outcome did not display the data like we expected. Instead, we used an online tool called [CSV Plots](https://www.csvplot.com/) to map our data in a line graph. 

| Dhows Sailed  |
|---|
|  ![Dhows Sailed](/assets/images/assignment2/Graph_Line_Dhows_Sail.png) |
| Dhows Arrived  |
| ![Dhows Arrived](/assets/images/assignment2/Graph_Line_Dhows_Arrive.png)  |


## Conclusion
This assignment has allowed us to learn more about AI, specifically its capabilities of doing humanities tasks. On first glance, we did not identify any major conclusions from our data. Rather than not having enough information, it lies at the point that nothing particularly ‘interesting’ surfaced from the shipping records.However, through closer inspection and contextual analysis, we were able to identify meaningful patterns—though these observations remain provisional and would require further research beyond our dataset to confirm. Zanzibar, in 1909, stood as a vital maritime trade hub in East Africa. Although under British colonial rule at the time, it maintained strong commercial ties with Arabian traders, particularly those from Oman. The high number of Zanzibar/British dhows indicates local dominance in maritime activity. We also took into account external influences that might affect the data, such as:
- **Seasonal Trade Routes:** Maritime trade was heavily influenced by monsoon patterns, particularly between March and May. Dhows from Arabia and India likely followed these seasonal wind cycles—evident in the noticeable drop in arriving dhows during these months.
- **Colonial Policies:** The dominance of British and Zanzibari dhows may have been shaped by colonial policies that favored local or colonial-affiliated traders, potentially limiting foreign competition.
- **German Presence:** The presence of German dhows could be linked to the presence of German East Africa at the time, which encompassed modern-day Rwanda, Burundi, mainland Tanzania, and a small section of Mozambique.
- **Relative Influence:** Arabian and German traders demonstrated moderate activity, while French traders seemed to play a relatively minor role in Zanzibar’s maritime network.

Ultimately, while our project began as a technical exercise in digitization and data visualization, it gradually revealed layers of historical insight—underscoring how even seemingly mundane records can illuminate broader narratives when combined with careful analysis and contextual understanding.


## Contributions
*On this assignment, Ahmad prompted the AI chatbots, created the .csv file Google Sheets, and Dhows graph. Lucas visualized the main table (Shipping Report) into Kepler. We both refined the shipping report table and wrote the markdown post together.*

## Resources
Klein, Lauren, et al. "Provocations from the humanities for generative ai research." arXiv preprint arXiv:2502.19190 (2025).
The Editors of Encyclopaedia Britannica. "German East Africa". Encyclopedia Britannica, 15 Oct. 2024, https://www.britannica.com/place/German-East-Africa. 
