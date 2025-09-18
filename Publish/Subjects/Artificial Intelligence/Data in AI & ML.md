---
Title: Data in AI & ML
Status: 
marker:
  - "[[Artificial Intelligence Index]]"
tags: 
Date: 2025.08.05
Time: 14:15
---
# Data in AI & ML
Data can be any unprocessed fact, value, text, sound, or picture that is not interpreted or analyzed.

## Sources
- Databases
- APIs
- Web Scraping
- Data Streams
- Sensors and IoT Devices
- Log Files
- Social Media

## Sources Classification
We can classify the data source on the basis of this.
- **Primary Data**
  - Collected directly from first-hand experience
  - Examples: Surveys, experiments, census data from government
- **Secondary Data**
  - Data that has to be scraped, obtained, or collected and pre-processed
  - Examples: Research articles, existing databases, public records

## Types of Data
- **Quantitative Data**
  - Represented through numbers
  - **Discrete Data:**
    - Countable items
    - Examples: Number of houses in a city, number of followers
  - **Continuous Data:**
    - Measurable and can have any value within a range
    - Examples: House prices in a city, sale prices

- **Qualitative Data**
 - Represented via words and descriptions
 - **Nominal Data:**
   - Categories without any order
   - Examples: Genres, types, colors, nationality
 - **Ordinal Data:**
   - Categories with a meaningful order or ranking
   - Examples: Rankings, scores, survey responses (e.g., strongly agree, agree, neutral, disagree, strongly disagree)
- **Unprocessed Data**	- Raw data that has not been cleaned or analyzed.

- **Unstructured Data**:
  - **Image**:
    - Typically stored in non-relational databases or specialized image storage systems.
    - Cannot be searched easily without metadata or image recognition techniques.
  - **Videos**:
    - Stored in various formats and often require large storage capacities.
    - Difficult to search without the aid of video processing and metadata tagging.
  - **Text**:
    - Includes documents, emails, social media posts, etc.
    - Stored in databases, file systems, or document management systems.
    - Searchable through text mining and natural language processing techniques.



## Data Issues in ML
- **Data Quality:**
  - To ensure the data is accurate, complete, and representative.
  - Issues include:
    - Formatting errors
    - Typos
    - Redundancies
    - Missing entries
    - Irrelevant values

- **Data Quantity:**
  - Training a deep learning (DL) model requires a large amount of data.
  - The model may learn from the spacing between the data elements, leading to overfitting.

- **Bias and Fairness:**
  - To ensure that the training data is not biased or unrepresentative.
  - This can lead to unfair or biased outcomes.

- **Overfitting:**
  - Occurs when a model is too complex and fits the training data too closely.
  - Results in poor generalization to new data.
  - Example: A student learns every topic, even those not important for the exam.

- **Underfitting:**
  - Occurs when a model is too simple and does not capture all the relevant patterns in the data.
  - Example: A student learns every topic but the important ones for the exam.

## Data Properties
- **Data Quality:**
  - Good data should be:
    - Accurate: Correct and reliable, with minimal errors.
    - Complete: Missing values should be minimal or handled properly.
    - Representative: Covers all aspects of the problem domain (not just a subset).
    - Consistent: Same format, naming conventions, and units across the dataset.
    - Low Noise: Fewer irrelevant, misleading, or random variations in data.
- **Privacy and Security:**
  - Ensuring that sensitive information is protected and only accessible to authorized users.
  - Compliance with regulations and standards to maintain data integrity and confidentiality.

### Ensuring good quality in data
- **3Vs** of big data
	- Variety 
	- Velocity
	- Volume
- **Fitness of Use**
	- an evaluation to which extent some data serve the purpose of the user.
- **Survey**
	- Data scientists spend **80%** of time in finding, cleansing, organizing the data.
- **Characteristics of Data:**
	- **Completeness**
		- All of the required data is present.
		- Missing Data Handling
	- **Accuracy**
		- Data should reflect Reality
	- **Timeliness**
		- Data being available when it is needed for decision making.
	- **Consistency**
		- Data should 
		- Example birth date being DD-MM-YYYY in one data source and YY-MM-DD in other etc.
	- **Validity**
		- New Postal codes rendering Old postal codes out 
	- **Uniqueness**
		- Duplicates
# References
###### Information
- date: 2025-08-05
- time: 14:15
