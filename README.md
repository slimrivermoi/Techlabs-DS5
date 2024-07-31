# Düsseldorf Techlabs Data Science Team 5
### Project Team
---
- [Michael Fischer](https://github.com/michaeljordan53)
- [Chan Chham](https://github.com/ChanChham?query=slimrivermoi)
- [Muhammad Shamsher](https://github.com/Shamsher92)
- [Lee Yong](https://github.com/slimrivermoi)


### Our Project Mission
---
Using techniques we have learned in Data Science track to analyze, visualize and create data prediction based on ML model to make positive impacts in data science. 
We have been given 9 datasets (~ 1GB) related to movie and rating data from various sources (TMDB, IMDB, Open Source). At this point, we have yet to determine the specific problem we would like to tackle, the potential prediction target is movie rating prediction.


### Project Phases
---
Project Duration: 9 weeks (July 6 - Sep 1, 2024)

| Steps | Description | Timeline | Completion Date |
| ----------- | ----------- | ----------- | ----------- |
| 1 | Team and project setup | Week 1 | July 14 |
| 2 | Exploratory Data Analysis (EDA) | Week 2 | July 21 |
| 3 | data analysis | Week 3-4 | July 28 |
| 4 | Define problem that needs to be solved | Week 4-5 | Aug 5 |
| 5 | Model building and evaluation. | Week 6-7 | Aug 18 |
| 6 | Prepare for Presentation, complete all documentations | Week 8-9 | Sep 1 |

### Detailed Summary of the project (key milestones)
---
July 14:
  - Team setup, received project instructions, GitHub setup, etc.
  - The team set ground rules of engagement, clarify roles, connect Repo and Project on Github.
  - The team meet 2 times a week and use Slack as main communication channel.
  - Mathemetic formula comparisons for movie rating predictions.

July 20:
  - Team met to discuss respective prelim data analysis, data relationship mapping, data parsing and confirmed approach for our EDA (exploratory data analysis).
  - Identify tasks for further EDA to prepare for ML model building.

July 29:
  - Further improvement for file organization and data cleanup procedure in Github.
  - Finalized data cleanup procedure, dataset relationship mapping.
  - Begin exploration in text analysis with various techniques.

### Dataset Relationship Mapping
---
The team analyzed the given dataset and mapped the relationship based on identifiers from each respective files. [Dataset Relationship Mapping](https://github.com/slimrivermoi/Techlabs-DS5/blob/main/edit_data/Lee/Dataset_Relationship_Mapping%2029-07-24.png)

### Libraries Used
---
For data cleanup and data parsing:
- **ast.literal_eval():** to safely parse the JSON string into a Python object.  
- **datetime:** to convert variable to datetime format.
- **pathlib.Path:**  assign file paths when saving DF as CSV.
- **re:** parsing keywords in text inputs. 

For plotting:
- matplotlib.pyplot
- 

### API Used (if any)
---
Potential: 
- [TMDB Movies Recommendations](https://developer.themoviedb.org/reference/movie-recommendations)
- [TMDB reviews from user](https://developer.themoviedb.org/reference/movie-reviews)
### Algorithm
---

### Explanation of important code
---
**Parsing JSON String to Python Object (List/Dictionary):**
- This is an important task we must accomplish because multiple series in the datasets are in this format and we must convert them as features for the prediction target.
- **Using ast.literal_eval()** is the safest and most effective solution we have found to parse the JSON string safely without facing errors (e.g.: JSONDecode Error, TypeError and KeyError) or losing large chunk of data due to Try-Except bypass.
- See below for an example: 
```
import pandas as pd
import ast

keywords_df = pd.read_csv("../../source_data/keywords.csv")

# Function to parse the string and extract names
def extract_names(keyword_string):
    # Safely evaluate the string to a Python object
    keyword_list = ast.literal_eval(keyword_string)
    # Extract names
    names = [keyword['name'] for keyword in keyword_list]
    return names

# Apply the function to the DataFrame
keywords_df['names'] = keywords_df['keywords'].apply(extract_names)

# Display the DataFrame
keywords_df.head(20)
```

**Mathematics formula for Movie Ratings**
- [insert here]


### Team Space:
---
1. [Q&A](https://www.notion.so/Question-and-Issues-5783ec63fba843e698d1f9913926abe8)
2. [Detailed journal](https://www.notion.so/7f1283873ba049998330cb60b68acfd6?v=9c0d17e321bd4d738bf5ce479dbde791)

 
 
 

