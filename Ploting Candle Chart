import pandas as pd
from pandas import Series, DataFrame
import sqlite3
import matplotlib.pyplot as plt
import mplfinance as mpf

con = sqlite3.connect('c:/Users/sammy/stock.db')
df = pd.read_sql("SELECT * From 한국전력", con, index_col=None)

df = df.rename(columns = {'index' : 'date'})
df = df.sort_values(by = ['date'], ascending = True)
df['date'] = pd.to_datetime(df['date'])
df = df.set_index('date')

df1 = df.loc['20200501' : '20201031']
mpf.plot(df1, type = 'candle', title = 'KEPCO', mav = (5, 20, 60), volume = True, show_nontrading = True)
