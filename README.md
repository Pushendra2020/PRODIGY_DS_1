# PRODIGY_DS_1
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns

df = pd.read_csv('population_india_census2011.csv')
print(df.head())
print(df.columns)

population_by_state = df.groupby('State / Union Territory')['Population'].sum().reset_index()
population_by_state = population_by_state.sort_values(by='Population', ascending=False)

plt.figure(figsize=(15, 8))
sns.barplot(x='Population', y='State / Union Territory', data=population_by_state, palette='viridis')
plt.xlabel('Population')
plt.ylabel('State / Union Territory')
plt.title('Population by State / Union Territory (2011)')
plt.show()

gender_ratio_by_state = df.groupby('State / Union Territory')['Gender Ratio'].mean().reset_index()
gender_ratio_by_state = gender_ratio_by_state.sort_values(by='Gender Ratio', ascending=False)

plt.figure(figsize=(15, 8))
sns.barplot(x='Gender Ratio', y='State / Union Territory', data=gender_ratio_by_state, palette='coolwarm')
plt.xlabel('Gender Ratio')
plt.ylabel('State / Union Territory')
plt.title('Gender Ratio by State / Union Territory (2011)')
plt.show()

rural_population_by_state = df.groupby('State / Union Territory')['Rural population'].sum().reset_index()
rural_population_by_state = rural_population_by_state.sort_values(by='Rural population', ascending=False)

plt.figure(figsize=(15, 8))
sns.barplot(x='Rural population', y='State / Union Territory', data=rural_population_by_state, palette='crest')
plt.xlabel('Rural population')
plt.ylabel('State / Union Territory')
plt.title('Rural population by State / Union Territory (2011)')
plt.show()
