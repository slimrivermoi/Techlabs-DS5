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


### Abstract
We developed a comprehensive Movie Recommendation System from simple content-based filtering to text-cluster prediction model. Our system aims to enhance user experience by providing personalized movie recommendations based on users preferences and interests. 

### Introduction
We received 9 dataset containing information about movies, ratings, keywords, cast and crew information. Some databases have similar fields but with less data (45,000 vs. 5,000 rows of movie data) while others have data noise to be addressed . The issues we faced were:
- How are these datasets related to one another?
- What are the definitions for the variables? 
- Shall we build a movie recommendation or rating prediction system?

---
### Methods
**Dataset Understanding:** after verifying the data source and definition, we drafted a [Dataset Relationship Mapping](https://github.com/slimrivermoi/Techlabs-DS5/blob/main/edit_data/Lee/Dataset_Relationship_Mapping%2029-07-24.png). This helps us to understand which are the useful variables and how they are related to one another. 

**Data Preparation and JSON Parson:** we performed basic cleanup steps such as removing duplicate records, erroneous rows with mismatched labels and non-movie entries. In this phase, we used [ast.literal_eval()](https://docs.python.org/3/library/ast.html#ast.literal_eval) to parse JSON strings from variables such as genres, cast, crew, and keywords to extract useful data which are critical features of our model.

**Exploratory Data Analysis (EDA) and Data Visualization:** with Matplotlib and seaborn, we visualized rating distributions, genre popularity, and user behavior to uncover insights that would shape our recommendation strategies. Key findings included trends in user preferences (ratings), the impact of movie genres, data noise to be anticipated and the importance of certain features in driving recommendations.  

---
### Building the Recommendation System
We explored several ways to develop our movie recommendation system, knowing that users typically choose movies based on several approaches from simple genres filtering to cast/director name or keywords searches. Here are the 3 approaches we had developed.   

**Approach 1: Content based filtering [Link to Notebook]()** 

This method used basic query technique to return recommendations based on name of actor/actress, genre and years of release. The recommendation is then sorted by a variable called [“Popularity”](https://developer.themoviedb.org/docs/popularity-and-trending) which is an important metric developed by TMDB with sophisticated criteria to rank all-time-favorite movies. 

---
**Approach 2: Content-based KNN Classification Prediction with COSimilarity [Link to Notebook]()** 

This approach finds and visualizes similar movies based on their descriptions using text analysis (KNN and TF-IDF) and cosine similarity:
- **Step 1:** Combine Text Features: Merge movie taglines, overviews, and keywords into a single text string for each movie.
- **Step 2:** Vectorize Text Data: Use [TF-IDF vectorization](https://scikit-learn.org/stable/modules/generated/sklearn.feature_extraction.text.TfidfVectorizer.html) to convert the combined text into numerical representations that highlight important words.
- **Step 3:** Find Similar Movies: Apply the [Nearest Neighbors](https://scikit-learn.org/stable/modules/generated/sklearn.neighbors.KNeighborsClassifier.html) algorithm using cosine similarity to identify the top 5 movies similar to a given movie title.
- **Step 4:** Visualize Similarity (Optional): Plot the [cosine similarity](https://scikit-learn.org/stable/modules/generated/sklearn.metrics.pairwise.cosine_similarity.html) of the recommended movies in a 2D space to visually represent their relationship to the input movie
---

**Approach 3: Text-Cluster KNN Classification Prediction [Link to Notebook]()** 

This Natural Language Processing (NLP) model involves the following steps:
- **Step 1: Text Pre-Processing:** using Regex (RE) to ensure all texts related to the movie are formatted and stripped before being transformed.
- **Step 2: Vocabulary Extraction and Transformation:** through [TfidfVectorizer](https://scikit-learn.org/stable/modules/generated/sklearn.feature_extraction.text.TfidfVectorizer.html), the source text variable will undergo important steps such as vocabulary extraction, word counts and calculation of Inverse Document Frequency (IDF).
- **Step 3: Cluster Analysis with K-Means:** a cluster label is then assigned to each movie by using [K-Means text-clustering](https://scikit-learn.org/stable/auto_examples/text/plot_document_clustering.html#sphx-glr-auto-examples-text-plot-document-clustering-py) technique. 
- **Step 4: KNN Classifier Fitting:** using the [KNeighbours Classifier](https://scikit-learn.org/stable/modules/generated/sklearn.neighbors.KNeighborsClassifier.html) model, we conducted a test-train-split and fit our model.
---
 
### GUI Prototype with tkinter [Link to Notebook]()
In order to showcase our recommendation system, we built a simple GUI prototype to fit our model using tkinter. It is a basic Python toolkit that allows us to set up a simple GUI quickly.
 

