# PRODIGY_DS_1
import pandas as pd


data = {
    "Sno": [1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25, 26, 27, 28, 29, 30, 31, 32, 33, 34, 35, 36],
    "State / Union Territory": ["Uttar Pradesh", "Maharashtra", "Bihar", "West Bengal", "Madhya Pradesh", "Tamil Nadu", "Rajasthan", "Karnataka", "Gujarat", "Andhra Pradesh", "Odisha", "Telengana", "Kerala", "Jharkhand", "Assam", "Punjab", "Chhattisgarh", "Haryana", "Uttarakhand", "Himachal Pradesh", "Tripura", "Meghalaya", "Manipur", "Nagaland", "Goa", "Arunachal Pradesh", "Mizoram", "Sikkim", "Delhi", "Jammu and Kashmir", "Puducherry", "Chandigarh", "Dadra and Nagar Haveli and Daman and Diu", "Andaman and Nicobar Islands", "Ladakh", "Lakshadweep"],
    "Population": [199812341, 112374333, 104099452, 91276115, 72626809, 72147030, 68548437, 61095297, 60439692, 49577103, 41974218, 35003674, 33406061, 32988134, 31205576, 27743338, 25545198, 25351462, 10086292, 6864602, 3673917, 2966889, 2570390, 1978502, 1458545, 1383727, 1097206, 610577, 16787941, 12267032, 1247953, 1055450, 585764, 380581, 274000, 64473]
}

df = pd.DataFrame(data)
import pandas as pd


data = {
    "Sno": [1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25, 26, 27, 28, 29, 30, 31, 32, 33, 34, 35, 36],
    "State / Union Territory": ["Uttar Pradesh", "Maharashtra", "Bihar", "West Bengal", "Madhya Pradesh", "Tamil Nadu", "Rajasthan", "Karnataka", "Gujarat", "Andhra Pradesh", "Odisha", "Telengana", "Kerala", "Jharkhand", "Assam", "Punjab", "Chhattisgarh", "Haryana", "Uttarakhand", "Himachal Pradesh", "Tripura", "Meghalaya", "Manipur", "Nagaland", "Goa", "Arunachal Pradesh", "Mizoram", "Sikkim", "Delhi", "Jammu and Kashmir", "Puducherry", "Chandigarh", "Dadra and Nagar Haveli and Daman and Diu", "Andaman and Nicobar Islands", "Ladakh", "Lakshadweep"],
    "Population": [199812341, 112374333, 104099452, 91276115, 72626809, 72147030, 68548437, 61095297, 60439692, 49577103, 41974218, 35003674, 33406061, 32988134, 31205576, 27743338, 25545198, 25351462, 10086292, 6864602, 3673917, 2966889, 2570390, 1978502, 1458545, 1383727, 1097206, 610577, 16787941, 12267032, 1247953, 1055450, 585764, 380581, 274000, 64473]
}

df = pd.DataFrame(data)
import matplotlib.pyplot as plt


df_sorted = df.sort_values(by="Population", ascending=False)




plt.figure(figsize=(12, 8))
bars = plt.barh(df_sorted["State / Union Territory"], df_sorted["Population"], color='skyblue')


for bar in bars:
    plt.text(
        bar.get_width(), 
        bar.get_y() + bar.get_height() / 2, 
        f'{bar.get_width():,}', 
        va='center', 
        ha='left'
    )

plt.xlabel('Population')
plt.ylabel('State / Union Territory')
plt.title('Population of Indian States and Union Territories (2011)')
plt.gca().invert_yaxis()  
plt.grid(axis='x', linestyle='--', alpha=0.7)
plt.show()

import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns

population_data = {
    "State": ["Maharashtra"],
    "Population": [112374333]
}

df_population = pd.DataFrame(population_data)


age_distribution = {
    "0-14": 0.30,
    "15-24": 0.20,
    "25-54": 0.40,
    "55-64": 0.05,
    "65+": 0.05
}


for age_group, percentage in age_distribution.items():
    df_population[age_group] = df_population["Population"] * percentage

df_population = df_population.melt(id_vars=["State", "Population"], var_name="Age Group", value_name="Population Count")


plt.figure(figsize=(10, 6))
sns.barplot(x='Age Group', y='Population Count', data=df_population, palette='viridis')
plt.xlabel('Age Group')
plt.ylabel('Population Count')
plt.title('Age Distribution in Maharashtra (2011)')
plt.show()
