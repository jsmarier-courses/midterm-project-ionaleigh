**2024-10-16**<br>
**MPAD2003A Itroductory Data Storytelling**<br>
**Iona Munro**<br>
**Presented to Jean-Sébastien Marier**<br>

# Midterm Project: Exploratory Data Analysis (EDA)

Use one hashtag symbol (`#`) to create a level 1 heading like this one.

## Foreword

For this assignment, you must extract data from a dataset provided by the instructor. You must then clean and analyze the data, create exploratory charts/visualizations, and find a potential story idea. Your assignment must clearly detail your process. You are expected to write about 1500-2000 words, and to include several screen captures showing the different steps you went through. Your assignment must be written with the Markdown format and submitted on GitHub Classroom.

I have been assigning different versions of this project to my digital journalism and data storytelling students for a few years now. Its structure was inspired by the main sections/chapters of [*The Data Journalism Handbook*](https://datajournalism.com/read/handbook/one/). This version was further inspired by the [Key Capabilities in Data Science](https://extendedlearning.ubc.ca/programs/key-capabilities-data-science) program offered by the University of British Columbia (UBC).

**Here are some useful resources for this assignment:**

* [GitHub's *Basic writing and formatting syntax* page](https://docs.github.com/en/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax)
* [The template repository for this assignment in case you delete something by mistake](https://github.com/jsmarier/jou4100_jou4500_mpad2003_project2_template)

Did you notice how to create a hyperlink? In Markdown, we put the clickable text between square brackets and the actual URL between parentheses.

And to create an unordered list, we simply put a star (`*`) before each item.

## 1. Introduction

This project focuses on a City of Ottawa dataset regarding **service requests related to municipal operations**. The dataset covers requests submitted between **August 1, 2024, and September 1, 2024.** It was collected by the City through **resident submissions via various channels, including walk-ins, phone calls, and emails**. It includes details such as **service request IDs, statuses (e.g., resolved, active), types of requests (e.g., bylaw services, road maintenance, garbage collection), descriptions, opened and closed dates, addresses, geographic coordinates (latitude and longitude), and the method of submission**. 

The dataset can be accessed through the following links:

- [Original dataset on Open Ottawa](https://311opendatastorage.blob.core.windows.net/311data/311opendata_lastyear.csv)
- [CSV version on Github](https://raw.githubusercontent.com/jsmarier/course-datasets/refs/heads/main/ottawa-311-service-requests-august-2024.csv)

The main sections of this assignment will cover getting data, cleaning data, understanding data, and potential storytelling insights.

## 2. Getting Data

Steps to import the CSV file manually into Google Sheets:

1. **Download the CSV File:**
   - Right-click on the link: [ottawa-311-service-requests-august-2024.csv](https://raw.githubusercontent.com/jsmarier/course-datasets/refs/heads/main/ottawa-311-service-requests-august-2024.csv).
   - Select **"Save link as…"** and save the file to your computer.

2. **Open Google Sheets and Start a New Sheet**

3. **Import the CSV File:**
   - In Google Sheets, go to **File** > **Import**.
   - Select **Upload**, then click **Select a file from your device** and locate the CSV file you downloaded.
   
4. **Set Import Options:**
     - Choose **Replace spreadsheet** to load the CSV data into the new sheet.
     - Under **Separator type**, select **Comma** to ensure the columns load correctly.
     - Click **Import data**.

![Imported dataset](MPAD2003A%20Midterm.png)<br>
*Figure 1: Screenshot of the imported data with the first 26 rows visible.*
[Link to my Google Sheets dataset](https://docs.google.com/spreadsheets/d/17jH3OmQ0WeL8HybLJtdWWPSTpL6A71DkrbgjlCyel3U/edit?usp=sharing)

### General Observations

1. **Structure of the Data**:
   - The dataset contains **11 columns** and **28,539 rows**. This large number of rows indicates a substantial collection of service requests over time.

2. **Cleanliness of the Data**:
   - Overall, the data appears to be organized with clear headings and defined columns. However, there are some values represented as `\N`, which likely indicates missing, undefined, or corrupted data.

3. **Specific Column Observations**:
   - **Column A (Service Request ID)**: Features **nominal variables** representing unique identifiers for each service request. This column is crucial for tracking individual requests.
   - **Column B (Status)**: Contains **ordinal/nominal variables** indicating the current status of each request (e.g., Resolved, Active, Cancelled). This column provides insight into the resolution process of municipal operations.
   - **Column C (Type)**: Includes **nominal variables** detailing the category of service requests (e.g., Garbage and Recycling, Bylaw Services). The variety in this column reflects the range of services provided by the City of Ottawa.

4. **Observations of Interest**:
   - The presence of multiple requests with the same status but different types (e.g., various Garbage and Recycling requests) suggests that certain types of requests are more prevalent. 
   - There are several entries with missing values, particularly in the **Closed Date** and **Address** columns, which could affect analyses related to time taken to resolve requests and spatial analysis of service requests.

5. **Questions/Hypotheses**:
   - One question that arises is: **What factors contribute to the frequency of certain service request types?** 
   - Additionally, it would be interesting to investigate whether certain wards or areas of the city experience more requests than others, and if so, what might explain these differences.


<!-- Use two hashtag symbols (`##`) to create a level 2 heading like this one.

To include a screen capture, use the sample code below. Your images should be saved in the same folder as your `.md` file.

![](import-screen-capture.png)<br>
*Figure 1: Screenshot of the imported data with the first () rows visible.* -->

<!-- **Here are examples of functions and lines of code put in grey boxes:**

1. If you name a function, put it between "angled" quotation marks like this: `IMPORTHTML`.
1. If you want to include the entire line of code, do the same thing, albeit with your entire code: `=IMPORTHTML("https://en.wikipedia.org/wiki/China"; "table", 5)`.
1. Alternatively, you can put your code in an independent box using the template below:

``` r
=IMPORTHTML("https://en.wikipedia.org/wiki/China"; "table", 5)
```
This also shows how to create an ordered list. Simply put `1.` before each item. -->

## 3. Understanding Data

### 3.1. VIMO Analysis

Use three hashtag symbols (`###`) to create a level 3 heading like this one. Please follow this template when it comes to level 1 and level 2 headings. However, you can use level 3 headings as you see fit.

Insert text here.

Support your claims by citing relevant sources. Please follow [APA guidelines for in-text citations](https://apastyle.apa.org/style-grammar-guidelines/citations).

**For example:**

As Cairo (2016) argues, a data visualization should be truthful...

### 3.2. Cleaning Data

Insert text here.

### 3.3. Exploratory Data Analysis (EDA)

Insert text here.

**This section should include a screen capture of your pivot table, like so:**

![](pivot-table-screen-capture.png)<br>
*Figure 2: This pivot table shows...*

**This section should also include a screen capture of your exploratory chart, like so:**

![](chart-screen-capture.png)<br>
*Figure 3: This exploratory chart shows...*

## 4. Potential Story

Insert text here.

## 5. Conclusion

Insert text here.

## 6. References

Include a list of your references here. Please follow [APA guidelines for references](https://apastyle.apa.org/style-grammar-guidelines/references). Hanging paragraphs aren't required though.

**Here's an example:**

Bounegru, L., & Gray, J. (Eds.). (2021). *The Data Journalism Handbook 2: Towards A Critical Data Practice*. Amsterdam University Press. [https://ocul-crl.primo.exlibrisgroup.com/permalink/01OCUL_CRL/hgdufh/alma991022890087305153](https://ocul-crl.primo.exlibrisgroup.com/permalink/01OCUL_CRL/hgdufh/alma991022890087305153)
