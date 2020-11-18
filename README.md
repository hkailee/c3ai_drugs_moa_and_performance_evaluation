# C3.ai Therapeutic Agents/Drugs Mechanism of Action (MOA) and Performance Evaluation  
Repurposing of existing therapeutic agents (TAs) previously designed for other virus infections are being put on trials for the COVID19 patients for immediate disease control and management. A quick global overview on mechanism of action (MOA) and current status of the trials in terms of efficacy and safety is required for strategic life-saving and resource plannings. The planning managers or applicants of the treatments need to monitor both qualitative and quantitative growth of textual data objectively and make strategic decisions based on how situations, as depicted in the scientific reports, evolve. 

## Broad strategies covered
All abstracts available from the COVID-19 Open Research Dataset (CORD-19) were pre-processed to obtain Word2Vec embeddings using SkipGram model. The embeddings was used to calculate the nearest neighbours of the keywords using cosine similarities. 

Here, within the dimensional space of the Word2Vec embeddings, terms with similar context as well as forward-looking/backward-looking were assumed to cluster closer to a TA with varying degrees. Briefly, deep walking was first performed (10-nearest-words retrieval) on the study terms consisted of TAs and sentimental terms (consisted of positive and negative sentiment terms available), followed by subsequent 100 nearest words retrieval on the 10 nearest words retrieved from the previous study terms. 

To derive the sparse relations between TAs and sentimental words, Pearson correlations between the study terms were computed according to the appearance of the words retrieved from the deep walkings. Lastly, the aggregate correlation scores for positive, negative, and uncertainty sentiments were relatively compared between the TAs. The results were validated using PubMed and medRxiv search.

## Installation
### Virtual environment using anaconda is recommended
```
$ conda create -n knowdisc_py36 python=3.6 -y
$ conda activate knowdisc_py36
$ conda install ipykernel jupyter -y; python -m ipykernel install --user --name knowdisc_py36 --display-name "knowdisc_py36"; 
```

### installation of necessary packages
```

$ pip install pymed chart_studio
$ pip install wordcloud
$ pip install facets-overview
$ pip install seaborn scikit-learn statsmodels numba
$ pip install scanpy[leiden]
```

OR

```
$ pip install -r requirements.txt
```


## Folder structure
    .
    ├── Data/                # Contains data used in this study (download links in WorkBook.ipynb)
          └── figures/       # Contains figures generated in this study
    ├── WorkBook.ipynb        # Working notebook with codes used in this study
    ├── c3aidatalake.py      # A helper file shared across projects and quizzes
    ├── utils.py             # A helper utility file used in this project
    └── requirements.txt     # Common packages used for the packages

## Data
Data used in this study was mainly downloaded using C3.ai api for COVID-19 Grand Challenge.
The sentimental words dictionary used in this study are publicly available. 

## Resources
1. https://c3.ai/c3-ai-covid-19-grand-challenge
2. https://sraf.nd.edu/textual-analysis/resources/#LM%20Sentiment%20Word%20Lists
