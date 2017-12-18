# AWS

import numpy as np
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns

import os
import datetime as dt

%matplotlib inline

pd.set_option('display.max_columns', None)

DATASETS_PATH = os.path.join('..', 'datasets')
DATASETS_PATH

filename_users_prime = os.path.join(DATASETS_PATH, 'file.csv')
df_users_pri = pd.read_csv(filename_users_prime)

df_users_pri.shape

df_users_pri.info()

df_users_pri.describe()

df_users_pri.head()

df_users_pri.tail()

filename_users_classic = os.path.join(DATASETS_PATH, 'file2.csv')
df_users_classic = pd.read_csv(filename_users_classic)

df_users_classic.shape

df_users_classic.info()

np.setdiff1d(df_users_cla.columns, df_users_pri.columns)

df_users_classic.describe()

df_users_classic.head()

df_users_classic.tail()

filename_events = os.path.join(DATASETS_PATH, 'file3.csv')
df_events = pd.read_csv(filename_event

df_events.shape

df_events.info()

df_events.apply(lambda x: 1.0 - (x.isnull().sum().astype(float) / df_events.shape[0]))

df_events.head()

df_events.tail()

#######

df_users_prime['ID_Externo'].unique()

df_users_prime['ID_Externo'].nunique()

(df_users_prime['ID_Externo'] != '-').sum()

(df_users_prime['ID_Externo'] != '-').sum() / float(df_users_prime.shape[0])

df_users_prime.loc[df_users_prime['ID_Externo'] != '-'].sort_values('ID_Externo')

df_users_prime['Push_Token'].nunique()

(df_users_prime['Push_Token'] != '-').sum() / float(df_users_prime['Push_Token'].shape[0])

df_users_prime.loc[df_users_prime['Push_Token'] != '-'].sort_values('Push_Token') #['Push_Token'].tolist()

df_users_prime['CEClient'].value_counts()

sns.heatmap(df_corr)

sns.plt.figure(figsize=(15, 9))
sns.regplot(df_events['longitude'], df_events['latitude'], fit_reg=False)
