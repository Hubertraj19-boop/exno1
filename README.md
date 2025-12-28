# Exno:1
Data Cleaning Process

# AIM
To read the given data and perform data cleaning and save the cleaned data to a file.

# Explanation
Data cleaning is the process of preparing data for analysis by removing or modifying data that is incorrect ,incompleted , irrelevant , duplicated or improperly formatted. Data cleaning is not simply about erasing data ,but rather finding a way to maximize datasets accuracy without necessarily deleting the information.

# Algorithm
STEP 1: Read the given Data

STEP 2: Get the information about the data

STEP 3: Remove the null values from the data

STEP 4: Save the Clean data to the file

STEP 5: Remove outliers using IQR

STEP 6: Use zscore of to remove outliers

# Coding and Output

import pandas as pd 

df=pd.read_csv("data_set.csv")

df

<img width="1035" height="809" alt="image" src="https://github.com/user-attachments/assets/fbf283a4-e107-4133-9513-42ae821f5d4f" />
<img width="1109" height="263" alt="image" src="https://github.com/user-attachments/assets/6ab8a70a-019a-4bf5-9e6a-d843d8bb57be" />
<img width="1035" height="254" alt="image" src="https://github.com/user-attachments/assets/a0adde6d-9297-4000-bd2f-772959dc601d" />




df.isnull()
<img width="894" height="819" alt="image" src="https://github.com/user-attachments/assets/3e2a017d-5204-42f8-a61e-69c0f285b415" />


df.isnull().sum()

<img><img width="375" height="197" alt="image" src="https://github.com/user-attachments/assets/c7d362d0-5d05-4c42-9a62-784396adf16b" />

df.notnull()

<img><img width="1062" height="467" alt="image" src="https://github.com/user-attachments/assets/8a2a8faf-cef4-40a8-8f0d-11bb2ad8a744" />

print(df.dropna(axis=0))
<img width="1047" height="552" alt="image" src="https://github.com/user-attachments/assets/6b021a1a-e35d-46f3-b6b8-38e5b3b0d1c4" />


print(df.dropna(axis=1))
<img width="341" height="794" alt="image" src="https://github.com/user-attachments/assets/c1d97e25-c304-434e-a9ae-37a0ad3dacf0" />

dfs=df[df['num_episodes']>20]

dts

<img><img width="1013" height="650" alt="image" src="https://github.com/user-attachments/assets/d7b55276-2bdf-46c5-bcfb-421900dcd2a7" />

dfs=sd[sd['country'].str.startswith(('C'))&(df['num_values']>15)]

dt.fillna(0)
<img width="1064" height="819" alt="image" src="https://github.com/user-attachments/assets/a991791e-dbab-4183-8eb2-7557964f0c81" />

dt.fillna(method='ffill')
<img width="1053" height="802" alt="image" src="https://github.com/user-attachments/assets/98489b2b-c494-41e5-9233-34c7197fcd5c" />

ir=pd.read_csv("iris.csv")
ir
<img width="663" height="531" alt="image" src="https://github.com/user-attachments/assets/811658ec-8250-4b26-aae8-60fb9272a2bc" />

import seaborn as sns
sns.boxplot(x="sepal_width",data=ir)
<img width="831" height="667" alt="image" src="https://github.com/user-attachments/assets/d930e02d-ae47-4c61-af59-2788375aa0d8" />

q1=ir.sepal_width.quantile(0.25)
q3=ir.sepal_width.quantile(0.75)
iqr=q3-q1
rid=ir[((ir.sepal_width<(q1-1.5*iqr))|(ir.sepal_width>(q3+1.5*iqr)))]
rid['sepal_width']
<img width="621" height="156" alt="image" src="https://github.com/user-attachments/assets/45b4f540-635c-46b1-b209-925da1979b97" />

rid=ir[~((ir.sepal_width<(q1-1.5*iqr))|(ir.sepal_width>(q3+1.5*iqr)))]
rid
<img width="633" height="507" alt="image" src="https://github.com/user-attachments/assets/11f89d25-5f4f-416f-8440-7d3235e530ec" />

rid=ir[((ir.sepal_width>(q1-1.5*iqr))&(ir.sepal_width<(q3+1.5*iqr)))]
rid['sepal_width']
<img width="687" height="320" alt="image" src="https://github.com/user-attachments/assets/8b5e42f7-e218-41cb-b330-55f133a75df0" />

import scipy.stats as stats
z=np.abs(stats.zscore(ir.sepal_width))
z
![Uploading image.png…]()

RESULT
Thus we have cleaned the data and removed the outliers by detection using IQR and Z-score method.


