**2024-10-16**<br>
**MPAD2003A Introductory Data Storytelling**<br>
**Iona Munro**<br>
**Presented to Jean-Sébastien Marier**<br>

# Midterm Project: Exploratory Data Analysis (EDA)

<!-- ## Foreword -->

<!-- For this assignment, you must extract data from a dataset provided by the instructor. You must then clean and analyze the data, create exploratory charts/visualizations, and find a potential story idea. Your assignment must clearly detail your process. You are expected to write about 1500-2000 words, and to include several screen captures showing the different steps you went through. Your assignment must be written with the Markdown format and submitted on GitHub Classroom.

I have been assigning different versions of this project to my digital journalism and data storytelling students for a few years now. Its structure was inspired by the main sections/chapters of [*The Data Journalism Handbook*](https://datajournalism.com/read/handbook/one/). This version was further inspired by the [Key Capabilities in Data Science](https://extendedlearning.ubc.ca/programs/key-capabilities-data-science) program offered by the University of British Columbia (UBC).

**Here are some useful resources for this assignment:**

* [GitHub's *Basic writing and formatting syntax* page](https://docs.github.com/en/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax)
* [The template repository for this assignment in case you delete something by mistake](https://github.com/jsmarier/jou4100_jou4500_mpad2003_project2_template)

Did you notice how to create a hyperlink? In Markdown, we put the clickable text between square brackets and the actual URL between parentheses.

And to create an unordered list, we simply put a star (`*`) before each item. -->

## 1. Introduction

This project focuses on a City of Ottawa dataset regarding **service requests related to municipal operations**. The dataset covers requests submitted between **August 1, 2024, and September 1, 2024.** It was collected by the City through **resident submissions via various channels, including walk-ins, phone calls, and emails**. It includes details such as **service request IDs, statuses (e.g., resolved, active), types of requests (e.g., bylaw services, road maintenance, garbage collection), descriptions, opened and closed dates, addresses, geographic coordinates (latitude and longitude), and the method of submission**. 

The dataset can be accessed through the following links:

- [Original dataset on Open Ottawa](https://311opendatastorage.blob.core.windows.net/311data/311opendata_lastyear.csv)
- [CSV version on Github](https://raw.githubusercontent.com/jsmarier/course-datasets/refs/heads/main/ottawa-311-service-requests-august-2024.csv)

The main sections of this assignment will cover getting data, cleaning data, understanding data, and potential storytelling insights.

---

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

![Imported dataset](MPAD2003A%20Midterm.png)
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

---

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

<!-- Use three hashtag symbols (`###`) to create a level 3 heading like this one. Please follow this template when it comes to level 1 and level 2 headings. However, you can use level 3 headings as you see fit. -->
<!-- Insert text here.
Support your claims by citing relevant sources. Please follow [APA guidelines for in-text citations](https://apastyle.apa.org/style-grammar-guidelines/citations). -->

This analysis evaluates the quality, accuracy, and reliability of the dataset using the VIMO framework (Validity, Integrity, Meaningfulness, and Organization), focusing on the columns **Status**, **Type**, and **Channel**.

---

#### 1. Validity

- **Status**: The "Status" column predominantly contains "Resolved," "Active," and "Cancelled" entries, which are clear and consistent indicators of each request’s completion status. However, further validation would be beneficial to ensure that all "Resolved" requests genuinely met resolution criteria.
- **Type**: Categories like "Garbage and Recycling," "Parking Control," and "Bylaw Services" appear valid, matching common municipal service types. However, some categories are broad, which could impact the specificity of any analysis.
- **Channel**: Channels such as "Dispatch," "Web," "Walk-In," "Email," and "Voice In" are typical ways residents might interact with city services. Each channel appears valid for this context, though verifying that entries accurately reflect the method used for each request would enhance validity.

  **Example**: The "Resolved" status on a request (e.g., request ID 202457114472 row 387) that closed on the same day it was opened may raise questions about the accuracy of the resolution date.

*Analyzing datasets like this with an "interview" approach—asking questions of each column and value—is essential to validate its reliability and usefulness for storytelling or trend analysis (Eads, 2015).*

---

#### 2. Integrity
- **Missing Values**: The dataset contains numerous missing values (`\N`) in columns like "Address," "Latitude," and "Longitude," which limits the completeness of location data.
- **Consistency**: There may be inconsistencies in the "Type" column, where the same service type might be recorded differently (e.g., “Garbage and Recycling” vs. “Garbage/Recycling”). Ensuring standardization across entries would improve integrity.
- **Channel Consistency**: Channels are generally consistent with standard options, but it's important to ensure each request is linked to only one primary channel and that entries match the actual method used.

  **Example**: Requests with "Walk-In" as the channel but missing location details (e.g., address or coordinates) could indicate data entry issues and reduce the dataset's overall integrity.

---

#### 3. Meaningfulness
- **Status**: The "Status" column provides clear, meaningful information about each request's completion. However, without specific resolution dates, "Resolved" entries may lack sufficient detail to convey how long issues took to address.
- **Type and Channel**: The "Type" and "Channel" columns add meaningful context about the nature and reporting method of each request, helping identify trends in how citizens interact with services. For instance, the different channels indicate various ways people access city services, revealing preferences that could inform service improvement.

  **Example**: The "Cancelled" status on request ID 202457115065 could indicate duplication, error, or resolution through other means, but without further detail, its meaning may be unclear.

*As Cairo (2016) notes, choosing a graphical form to represent such nuanced data can greatly aid in meaningful analysis; visual cues like proportion and color can help clarify the magnitude and patterns in a way simple tables cannot.*

---

#### 4. Organization
- **Column Arrangement**: Columns are arranged logically, starting with request details (e.g., "Status," "Type") and followed by location details (e.g., "Address," "Latitude"), which helps with data interpretation.
- **Channel Diversity**: Having a range of channels (e.g., "Dispatch," "Web," "Walk-In," "Email," "Voice In") in one column makes the data easy to analyze and simplifies pattern detection. To enhance organization, it may help to group requests by channel to see which are associated with faster resolutions or cancellations.

  **Example**: Grouping "Channel" types in relation to "Status" could reveal patterns, such as certain channels (e.g., "Dispatch" vs. "Web") being linked to quicker response times.

---

### 3.2. Cleaning Data

In this section, I will detail the steps taken to clean the dataset effectively. The cleaning process involved several actions to ensure that the data was accurate, readable, and well-structured. Below are the specific steps I implemented:

#### 1. Deleting Empty Columns

- I **removed the empty columns** L and M from the dataset. This helped to streamline the data, making it easier to analyze and visualize.

#### 2. Concatenating Open - Close Dates

- I **combined columns E and F** into a single column labeled "Open - Close Date | Date d'ouverture - fermeture". The following formula was used to achieve this:

    `=CONCATENATE(H2, ", ", I2)`

- Additionally, to format the dates correctly, I used the following formula:

    `=TEXT(E2, "yyyy-mm-dd") & ", " & TEXT(F2, "yyyy-mm-dd")`

- This approach ensures that the dates are presented in a consistent format.

#### 3. Concatenating Latitude and Longitude

- I **concatenated** columns H and I, which contained Latitude and Longitude data, using this formula:

    `=CONCATENATE(E2, " - ", F2)`

#### 4. Validating Service Requests

- I checked that all service requests contained **valid numbers** by searching for any invalid entries using the following function:

    `=IF((ISNUMBER(A2)), "Valid", "Invalid")`

- This method allowed me to ensure that all service request IDs were numeric.

#### 5. Trimming Whitespace

- I **trimmed whitespace** from 758 selected cells using the built-in Google Sheets function to improve the data's clarity and consistency.

#### 6. Spell Check for Status Column

- I applied a **spell check function** for column B, which contains the status of service requests. I highlighted any words that did not match the acceptable statuses ("Resolved", "Active", "Cancelled") in red. The following function was used:

    `=ISERROR(MATCH(B2, {"Resolved", "Active", "Cancelled"}, 0))`

#### 7. Conditional Formatting for Status

- I implemented **conditional formatting** in column B to color code the status of requests. This visually differentiates the statuses, enhancing readability.

#### 8. Replacing Invalid Entries

- **I found and replaced 77,641** instances of ‘\N’ with **NULL** for clarity (except in column C where *Unspecified* was used in place of NULL for 2 instances to provide clarity in later pivot table). This was done using CTRL+F and the Find and Replace feature.

#### 9. Highlighting NULL Cells

- I applied **conditional formatting** to make NULL (and *Unspecified*) cells slightly red, allowing for quick identification of missing data.

#### 10. Text Wrapping

- Finally, I enabled **text wrapping** for smaller cells, such as those in column F, to enhance readability and presentation of the data.

By following these steps, I ensured that the dataset was clean, organized, and ready for analysis.

![Cleaned dataset](MPAD2003A%20Cleaned.png)
*Figure 2: Screenshot of the cleaned data with the first 24 rows visible.*

---

### 3.3. Exploratory Data Analysis (EDA)

#### 3.3.1 Pivot Table

The following **pivot table** summarizes the number of service requests categorized by type, providing a comprehensive view of the issues most frequently reported by residents. By organizing the data into key categories, we can identify patterns and trends in service requests that highlight the areas of concern within the community. The following sections outline the rationale behind selecting specific variables, key findings from the data, and insights into potential next steps for further investigation.

![Pivot table](MPAD2003A%20Pivot.png)
*Figure 3: Pivot table showing the number of service requests per type in basic numerical and percentage format.*

1. **Why did you choose these variables in particular?**
   - I chose to analyze the **Type** of service requests because it provides insight into the types of issues being reported to the city of Ottawa. Understanding the distribution of service requests allows us to identify which areas are most frequently engaged by residents and where the city may need to focus its resources.

1. **Does a particular number or statistic stand out?**
   - The most significant statistic is the **Garbage and Recycling** category, which accounts for **10,257 requests**, making up **35.94%** of all service requests. This large proportion indicates that garbage and recycling services are a major concern for residents.

1. **What did you learn? What's the potential story here?**
   - The data suggests that waste management is a critical area for city services in Ottawa, as indicated by the high volume of service requests in **Garbage and Recycling**. This could imply issues related to waste disposal, recycling education, or perhaps even the city's infrastructure for handling waste. Additionally, **Bylaw Services** and **Roads and Transportation** also show substantial request counts (19.77% and 14.77%, respectively), suggesting these are other areas needing attention and potential improvements.

1. **Which variables and numbers would warrant further investigation (next step)?**
   - Further investigation into the **Garbage and Recycling** requests could help to understand the specific issues being reported (e.g., missed pickups, need for additional bins). Additionally, exploring the **Bylaw Services** requests could reveal trends in community compliance and enforcement issues. Analyzing seasonal trends in requests or demographic factors influencing service requests could provide valuable insights for city planning and resource allocation.

#### 3.3.2 Exploratory Chart

**This section should also include a screen capture of your exploratory chart, like so:**

![](chart-screen-capture.png)
*Figure 3: This exploratory chart shows...*

## 4. Potential Story

Insert text here.

## 5. Conclusion

Insert text here.

## 6. References

Include a list of your references here. Please follow [APA guidelines for references](https://apastyle.apa.org/style-grammar-guidelines/references). Hanging paragraphs aren't required though.

**Here's an example:**

Bounegru, L., & Gray, J. (Eds.). (2021). *The Data Journalism Handbook 2: Towards A Critical Data Practice*. Amsterdam University Press. [https://ocul-crl.primo.exlibrisgroup.com/permalink/01OCUL_CRL/hgdufh/alma991022890087305153](https://ocul-crl.primo.exlibrisgroup.com/permalink/01OCUL_CRL/hgdufh/alma991022890087305153)
