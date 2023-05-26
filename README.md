# Covid_19-data-analyis-in-pandas
Covid_19 data analyis in pandas
#import dataset
import pandas as pd
covid_19 = pd.read_csv (r"C:\Users\chioma\Downloads\python projects\covid_19_data.csv")

covid_19.shape

covid_19

#show not null values
covid_19.count()

#show null values
covid_19.isnull()

covid_19.head

covid_19.isnull().sum()

# LETS DO SUM VIRULIZATION

#for visulaization
import matplotlib.pyplot as plt

# for vitualization
import seaborn as sns

sns.heatmap(covid_19.isnull())
plt.show()

#Q1 show the number of confirmed death and recovery cases in each regoin, (use the groupby function) 

covid_19.head(3)

#using the groupby function for results 
covid_19.groupby('Region').sum().head(25)

#now lets get the confirm cases .(alpabaticaaly). colum names are sensitive
covid_19.groupby('Region')['Confirmed'].sum()

covid_19.groupby('Region')["Confirmed","Deaths"].sum()

#confriming case in ascending order
covid_19.groupby('Region') ['Confirmed'] .sum().sort_values (ascending=False).head(5)

#MINIMUM NO OF DEATH TOP 10
covid_19.groupby('Region') .Deaths.sum() .sort_values(ascending=True) .head(10)

#HOW MANY CONFRIM DATE CASES FROM DATE TO NOW
covid_19[ covid_19.Region == 'Pakistan']

covid_19[covid_19.Confirmed <10]

# REMOVE RECODE WICHE IS LESS THAN 10
covid_19[~(covid_19.Confirmed) < 10]

covid_19

