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

<img><img width="564" height="619" alt="image" src="https://github.com/user-attachments/assets/37bccb89-280c-4b0d-bece-d0e4d40cdf6d" />

print(df.dropna(axis=1))

<img><img width="448" height="227" alt="image" src="https://github.com/user-attachments/assets/a499e43c-92d5-49fa-ad54-dea78d2b8cf5" />

dfs=df[df['num_episodes']>20]

dts

<img><img width="1013" height="650" alt="image" src="https://github.com/user-attachments/assets/d7b55276-2bdf-46c5-bcfb-421900dcd2a7" />

dfs=sd[sd['country'].str.startswith(('C'))&(df['num_values']>15)]

dfs

<img><img width="1006" height="670" alt="image" src="https://github.com/user-attachments/assets/6d71624f-5ff0-4573-8af7-8fdcba383aee" />

df.iloc[:4]

<img><img width="990" height="150" alt="image" src="https://github.com/user-attachments/assets/ec3d507b-4c58-443f-ad62-c039ea60edc8" />

df.iloc[[1,3,5],[1,3]]

<img><img width="296" height="127" alt="image" src="https://github.com/user-attachments/assets/a5ea78d9-abc2-4dc7-a6f5-252d2fffe876" />

df.iloc[0:4,1:4]

<img><img width="377" height="154" alt="image" src="https://github.com/user-attachments/assets/b12c56f7-af99-4a54-bdee-7e53a6f8fa7c" />

dff=df.fillna(0)

dff

<img><img width="984" height="375" alt="image" src="https://github.com/user-attachments/assets/2eec1600-9cb9-4a56-9c71-62b8d401735f" />

df.fillna(method='ffill')

<img><img width="993" height="383" alt="image" src="https://github.com/user-attachments/assets/8dec4637-a432-417a-b078-4f8cd0c3563c" />

df.fillna(method='bfill')

<img><img width="970" height="429" alt="image" src="https://github.com/user-attachments/assets/ee250810-fa04-4229-82d5-07fcd930067d" />

df['num_episodes'].fillna(value=df['num_episodes'].mean())

<img><img width="355" height="207" alt="image" src="https://github.com/user-attachments/assets/82650752-7e22-4e77-96c2-0e731a3fed5f" />

df['num_episodes'].fillna(value=df['num_episodes'].mean(),inplace=False)

<img><img width="356" height="201" alt="image" src="https://github.com/user-attachments/assets/584a453a-7044-49eb-9f13-329fedaf6e52" />

import matplotlib.pyplot as plt
plt.bar(df["country"],df["num_episodes"])

plt.show()

<img><img width="592" height="389" alt="image" src="https://github.com/user-attachments/assets/36cbab6b-7b24-45f8-ae4c-b6810d07284e" />

plt.barh(df["country"],df["num_episodes"])

plt.show()

<img><img width="701" height="384" alt="image" src="https://github.com/user-attachments/assets/43920211-b3cd-4dee-a3f3-3f4c40363704" />

plt.plot(df["country"],df["num_episodes"])

plt.show()

<immg><img width="628" height="390" alt="image" src="https://github.com/user-attachments/assets/83d1c527-1e20-4874-8c9a-af9e41741ce3" />

plt.scatter(df["country"],df["num_episodes"])

plt.show()

<img><img width="619" height="380" alt="image" src="https://github.com/user-attachments/assets/245b6959-86b2-41da-b14e-c4d2f2b30c7f" />
      

# Result

 The Data cleaning process is completed successfuly

