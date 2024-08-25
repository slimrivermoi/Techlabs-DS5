# Düsseldorf Techlabs Data Science Team 5 - The Data Avengers
**Project Mission:** to analyze, visualize and create data prediction model to make movies recommendations.

#### Project Team 
---
- [Michael Fischer](https://github.com/michaeljordan53)
- [Chan Chham](https://github.com/ChanChham?query=slimrivermoi)
- [Lee Yong](https://github.com/slimrivermoi)


#### Project Phases
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


#### Detailed Summary of the project (key milestones)
---
July 14:
  - Team setup, received project instructions, GitHub setup, etc.
  - The team set ground rules of engagement, clarify roles, connect Repo and Project on Github.

July 20:
  - Team met to discuss respective prelim data analysis, data relationship mapping, data parsing and confirmed approach for our EDA (exploratory data analysis).

July 29:
  - Further improvement for file organization and data cleanup procedure in Github.
  - Finalized data cleanup procedure, dataset relationship mapping.
  
Aug 5: 
  - Begin proper Exploratory Data Analysis (EDA) and basic recommendation system based on non ML model.

Aug 12: 
  - Explore various techniques for model building.
  - techniques include: basic filtering, KNN regression (to predict rating), K-Means Clustering, KNN-classifier, etc.
  - GUI prototype completed.

Aug 19:
  - Basic models in various methods completed. Discussed evaluation and finetuning.
  - Prepare for project submission and presentation.

### Dataset Relationship Mapping
---
- A total of 9 datasets (~ 1GB) related to movie and rating data from various sources (TMDB, IMDB, Open Source) were provided to the team.
- The team analyzed the given dataset and mapped the relationship based on identifiers from each respective files. [Dataset Relationship Mapping](https://github.com/slimrivermoi/Techlabs-DS5/blob/main/edit_data/Lee/Dataset_Relationship_Mapping%2029-07-24.png)


## Explanation of Models
#### Approach 1: Content filter based
---
- Author: [enter your name here]
- [insert here]: explain library used, algorithm steps, etc. 

#### Approach 2: Collaborative Content Predictive Model
---
- Author: [enter your name here]
- [insert here]: explain library used, algorithm steps, etc. 

#### Approach 4: Text-Cluster Classification Prediction Model
---
Author: Lee Yee Yong
**Link to Notebook: Insert here**
- This basic Natural Language Processing (NLP) model involves the following steps:
  - **Step 1: Text Pre-Processing:** using Regex (RE) to ensure all texts related to the movie are formatted and stripped before being transformed.
  - **Step 2: Vocabulary Extraction and Transformation:** through TfidfVectorizer, the source text variable will undergo 3 important steps such as vocabulary extraction, word counts and calculation of Inverse Document Frequency (IDF) which can be used as a feature for our model.  
  - **Step 3: Cluster Analysis with K-Means:** a cluster label is then assigned to each movie by using K-Means text-clustering technique. The assigned cluster label can now be used as our target (y) for prediction. As a result of this step, movies with relevant vocabularies now belong to certain clusters. 
  - **Step 4: KNN Classifier Fitting:** using the KNeighbours Classifier model, we defined the transformed text as the feature (X) and the cluster value as our target (y) and then transformed the data with the standard train-test-split at 75/25 (75% of data will be used for training, 25% would be used as test).
  - **Step 5: Prediction Model:** finally, we set up a query to ask user to provide a text input. The input will then be vectorized and fit into our model for prediction. 

 
 
 

