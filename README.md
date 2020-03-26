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
