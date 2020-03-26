# Twitter-pull-Covid-19
Covid 19 pull twitter 
from twitterscraper import query_tweets
import datetime as dt
import pandas as pd 

begin_date = dt.date(2020,2,25)
end_date = dt.date(2020,3,25)

limit = 1000
lang = "english"

tweets = query_tweets(" corona virus", begindate = begin_date, enddate = end_date, limit = limit, lang = lang)

**PLACE THE SCRIPT INSIDE A DATAFRAME AS SEEN BELOW**

df = pd. dataframe(t._dict_for t in tweets) 



**FOR MY SENTIMENT ANALYSIS FOR COVID-19 VIA TWwitter SEE BELOW**
import pandas as pd 
import datetime as dt
from twitterscraper import query tweets
from vadersentiment import SentimentIntensityAnalyzer
from langdetect import detect 
import matplotlib.pyplot as plt
import seaborn as sns

def detector(x): 
  try:
      return detect(x)
   except:
        None
        
#Build Analyzer Object
analyzer = SentimentIntensityAnalyzer()

#date range before onset 
begin_date = dt.date(2019,12,1)
end_date = dt.date(2020,1,15)

#after onset in america data range
begin_date_onset = dt.date(2020,1,15)
end_date_premier = dt.date(2020,3,25)

# query tweets with out parameters
tweets_before = query_tweets("#covid19", begindate = begin_date, endate= end_date, limit = 100000)
tweets_after = query_tweets("#covid19", begindate = begin_date_onset, endate = end_date_onset) 

**Convert to dataframe**
dt_before = pd.Dataframe(t._dict_for t in tweets_before)
df_after = pd.DataFrame (t._dict_for t in tweets_after)

**fILTER for english only**
df_before["lang"] = df_before ["text"].apply(lambda x:detector(x))
df_before = df_before(df_before ("lang")

**Actual sentiment analysis part**
sentiment_before = df_before[],.apply(lambda x: analyzer.polarity_scores(x))
sentiment_after_onset = df_after_onset[].apply(lambda x: analyzer.polarity_scores(x))

**put sentiment into dataframe**
df_before = pd.concat([df_before, sentiment_before.apply (pd.Series)], 1)
df_after_onset = pd.concat([df_after_onset, sentiment_after_onset.apply(pd.Series)])







