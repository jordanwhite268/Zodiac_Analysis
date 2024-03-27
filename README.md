# Introduction

One thing that has always intrigued me is the idea of different Zodiac signs having specific personality traits. While I can't say I put a lot of stock into horoscopes, I can't help but notice that there does seem to be some correlation between the personalities of people in my life and their signs.  Admittedly, the zodiac is not the most scientific of topics, but it is fun to think about, and worthy of some data analysis practice.  

In researching topics and datasets for this project, I came across a source that was produced by Harvard University's Pantheon Data Project that really fascinated me.  Compiled in 2016, this project represents a  "manually verified dataset of individuals that have transcended linguistic, temporal, and geographic boundaries'' and classifies them categorically by domain of accomplishment (e.g. Sports, the Arts, Science and Technology), Industry (e.g. Team Sports, Music, Medicine), and Occupation (e.g. Baseball Player, Composer, Psychologist).  The two above thoughts collided, and made me wonder:  if certain signs are predisposed to certain personality traits, does that mean that certain signs naturally gravitate to certain career paths?  And if so, is there a correlation between people who have excelled in certain areas and their Zodiac?  

# Features
## Loading Data 
This project includes 4 CSV datasets and 1 txt file that were cleaned and and processed within a Pandas dataframe and then loaded into a SQLite database.  
## Clean and Operate on data while combining them 
I used both Python and SQL to clean, transform, and join my data.
### Python Operations:  
I used a number of different methods to clean my data once the files were loaded into a Pandas Dataframe, including:
* Converting a date to date/time
* Converting date to the day of the year
* Dropping NAs
* Dropping unnecessary columns
* Df.loc[] and iloc[]
* String replacements
* Renaming columns
* Functions
* Concatenating
* Changing capitalization
* Forcing non-English characters into English characters
* Setting Indices
* Cast to numeric
### SQL operating and join
I created a custom field in both my main data sets (Famous_Birthdates.txt and Pantheon_People.csv) that combined the first three characters of a person’s first name with the first three characters of a person’s last name and birth year (e.g. JorWhi1989) to create a unique identifier from values in both datasets.  I then performed a SQL join and wrote this data to its own People table. 
* I wrote to SQL tables via Python
* I read in data from SQL tables via Python
* I updated SQL tables via python
## Visual/Present Data
## Best Practices
* I created a custom data dictionary for this project, which can be found in the repo as Zodiac_Analysis_Data_Dictionary.pdf.  
* I utilized a Virtual Environment.  Details on how to run can be found below.
## Interpretation of Data
I have annotated and commented my code in a Jupyter notebook so that it should be easy to follow and understand the steps being taken in each cell. 
GitHub Repository - My GitHub repository has 24 commits as of 3/26/24.

# How to Run
1. Clone the repo to your local machine. 
2. Create a virtual environment and install the packages listed in the requirements.txt file
   - Navigate to the folder in GitBash
   - Execute the following in GitBash:
      - For windows:  `python -m venv myvenv`
      - For Mac - `python3 -m venv myvenv`
3. Activate the virtual environment:
      `Cd myenv/scripts`
      `Source activate`
4. Install the required packages: `pip install -r requirements.txt`
5. Open the Jupyter notebook.  Click Run to run the code in each cell.  
   - There are several cells which read in data from the files in the repo.  If needed, change the file path to the    location of the repository on your local machine. 

Once you have finished, enter `deactivate` in GitBash to deactivate the virtual environment.


# Interpretation
In my dataset of over 10,000 people, there was a fairly equal distribution of the Zodiac signs, with the exception of Capricorns:

> [!WARNING]
> Add something about breakdown of signs here. 


In order to analyze my data, I used a proportional analysis to determine which combinations of signs and career paths were more prevelant. To do this, I calculated the percentage of people in the area with that zodiac sign, and subtracted the percentage of the zodiac sign of the total population.  With this calculation, I found the following to differ 2% or greater from the distribution in the total population: 


> [!WARNING]
> Add table here of signs that were prominent.

I excluded Exploration from my calculations due to a small sample size.  

Industries
Looking at the above areas and most prominent signs, I then dug further into the specific industries within the area with a larger proportion of people.  Because there were not equal numbers for each industry per area…. 



Use Calculations:
% of industry in area w/ Zodiac
% of industry in area overall.
