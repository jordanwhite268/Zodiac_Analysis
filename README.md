
![Jordan WHite Code Ky Capstone Project](https://github.com/jordanwhite268/Zodiac_Analysis/assets/66019293/3b6a34c8-b25f-476c-9fa1-712bbb75c918)

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
A Tableau story has been created and can be found here:  ***Need to insert link***
## Best Practices
* I created a custom data dictionary for this project, which can be found in the repo as Zodiac_Analysis_Data_Dictionary.pdf.  
* I utilized a Virtual Environment.  Details on how to run can be found below.
## Interpretation of Data
I have annotated and commented my code in a Jupyter notebook so that it should be easy to follow and understand the steps being taken in each cell. 

My GitHub repository has 24 commits as of 3/26/24.

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

![Zod Pie Chart](https://github.com/jordanwhite268/Zodiac_Analysis/assets/66019293/77cde574-fd99-47f3-b231-20f6507ade28)

## Definitions of the Zodiac
According to one source on the Zodiac (see data dictionary for more information), the signs have the following traits:

| Sign | Dates | Traits | 
| --- | --- | --- |
| Aries | March 21-April 19 | Competitive, Warm, Bold, Lively |
| Taurus | April 20-May 20 | Stubborn, Resolute, Grounded, Resilient |
| Gemini | May 21-June 20 | Curious, Witty, Communicative, Youthful |
| Cancer | June 21-July 22 | Emotional, Sentimental, Passionate, Loyal |
| Leo | July 23-August 22 | Dramatic, Courageous, Passionate, Charismatic |
| Virgo | August 23-September 22 | Practical, Analytical, Detail-focused, Desire to be helpful |
| Libra | September 23-October 22 | Artistic, Indecisive, Desire to maintain harmony and peace |
| Scorpio | October 23-November 21 | Mysterious, Intense, Passionate, Independent |
| Sagittarius | November 22-December 21 | Adventurous, Free-Spirited, Playful, Constantly seeking new wisdom and experiences |
| Capricorn | December 22-January 19 | Disciplined, Dedicated, Patient, Hardworking |
| Aquarius | January 20-February 18 | Truthful, Intelligent, Creative, Forward-Thinking |
| Pisces | February 19-March 20 | Empathetic, Intuitive, Understanding, Sensitive |


In order to analyze my data, I used a proportional analysis to determine which combinations of signs and career paths were more prevelant. To do this, I calculated the percentage of people in the area with that zodiac sign, and subtracted the percentage of the zodiac sign of the total population.  

These visualizations can be found here: 

## Prevalent Area/Zodiac Pairings - >= 2% Prevalence
### Business & Law
- Occupations Included: Lawyer, Business Person
- ***Leo*** - 3.2% greater prevalence than general population
-    Noteable people:  Mark Cuban, George Soros
- ***Capricorn*** - 8.4% greater prevalence than general population
-    Noteable people:  Jeff Bezos, Howard Hughes
### Humanities 
- Occupations Included:  Critic, Historian, Journalist, Philosopher, Writer  
- ***Capricorn*** - 3.6% greater prevalence than general population
-    Noteable people:  Edgar Allen Poe, Emily Bronte, Katie Couric
### Public Figures 
- Occupations Included:  Celebrity, Chef, Presenter/Host, Activist, Extremist
- ***Taurus*** - 3% greater prevalence than general population
-    Noteable People:  Jay Leno, Malcolm X, Jim Jones
 - ***Capricorn*** - 4.6% greater prevalence than general population
-    Noteable People:  Howard Stern, Frederick Douglass, Michelle Obama 

Exploration was excluded from calculations due to a small sample size.  

## Prevalent Occupation/Zodiac Pairings - >= 5% Prevalence
This analysis reviewed occupations with a total of 100 or more people and used the same calculations as above: 

| Area | Occupation | Zodiac Sign | Prevalence | Notable People |
| --- | --- | --- | --- | --- |
| Arts | Composer | Sagittarius | 5.7% | Caesar Franck, Giacomo Puccini, Jeal Sibelius, Ludwig van Beethoven, Scott Joplin |
| Humanities | Journalist | Capricorn | 16% | Charlie Rose, Katie Couric, Maureen Dowd, Max Frankel |
| Institutions | Military Personnel | Sagittarius | 7.5% | Charles de Gaulle |
| Public Figures | Social Activists | Capricorn | 8.6% | Frederick Douglass, Ira Glasser|
| Science & Technology  | Biologist | Gemini | 5.7% | Francis Crick |
| Sports | (American) Football | Scorpio | 6.1% | Troy Aikman, Phil Simms, Warren Moon |
| Sports | Basketball | Pisces | 6.7% | Charles Barkley, Julius Erving, Shaquille O’Neal |
| Sports | Coaching | Virgo | 6% | Marty Schottenheimer, Phil Jackson, Rick Pitino |
| Sports | Tennis | Gemini | 5.1% | Venus Williams, Rafael Nadal |

## Conclusion
One sign that is prominent through all these results is Capricorn.  Per the definitions in the data dictionary, Capricorns are disciplined, dedicated, patient, and hardworking, which are necessary traits to excel in any career path, but certainly also for Journalism, and the areas of Business and Law, etc.  Members of the military can be adventurous, and composers can be keen on seeking new experices, like their Sagittarius sign suggests. Biologists and Gemini are perhaps both curious and witty. But are basketball players (prominently Pisces) more empathetic and sensitive than football players (Scorpios)?  While one can make deductions from these correlations, there is certainly more nuance to one's personality and career path than can be captured in a few adjectives associated with a Zodiac sign.  Plus, being a pseudoscience, there is no one single definition of traits attributed to a sign; each source varies and there's no true authority on the matter.  So, interesting to think about, fun to discuss, of course. Annecdotally supported? Ok, sure.  But proven empirically? Maybe not...  

## Future Expansion
This project was a lot of fun to think about, and I think even without the Zodiac aspect, the People dataset that I created is functional and potentially has greater use.  I'd love to continue to add to it and bring in other demographics - birthplace, gender, etc., and I set up my database in such a way as to potentially add additional entries at a later date. I had also intitially intended to look more at Zodiac Elements (fire, earth, water, air) and things like moon signs and sun signs and all the different things one can explore within the Zodiac, but decided to leave them out due to time constraints. Maybe one of those will better unlock all the secrets of the Zodiac... 
