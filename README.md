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
```
import pandas as pd
d=pd.read_csv("/content/SAMPLEIDS (1).csv")
d
```

![image](https://github.com/user-attachments/assets/058ef683-8837-4787-967a-c3eeec897461)
d.isnull().sum()
![image](https://github.com/user-attachments/assets/f5b6edae-8123-4567-9376-013d2e257162)
d.isnull().any()
![image](https://github.com/user-attachments/assets/fbf32a80-c9db-4f12-b734-af9053af105f)
d.dropna()
![image](https://github.com/user-attachments/assets/a364d810-886e-4580-8918-c54acbef1746)
d.fillna(0)
![image](https://github.com/user-attachments/assets/a04f2c40-6fc7-4244-a537-e6e4118e424a)
d.fillna(method = 'bfill')
![image](https://github.com/user-attachments/assets/7ccbc364-4be1-46b7-b448-fd910e4b5e50)
df_dropped=d.dropna()
df_dropped
![image](https://github.com/user-attachments/assets/1e84aa94-603c-4ac4-8bf7-8ec2eefef5ca)
d.fillna({'GENDER':'MALE','NAME':'SRI','ADDRESS':'POONAMALEE','M1':98,'M2':87,'M3':76,'M4':92,'TOTAL':305,'AVG':89.999999})
![image](https://github.com/user-attachments/assets/bbd416fb-1bd6-47b1-96f3-ea2e87ae7444)
ir=pd.read_csv("/content/iris.csv")
ir
![image](https://github.com/user-attachments/assets/e90b1e98-d709-4daa-9742-f5ece75fd82f)
```
ir.describe()
```
![image](https://github.com/user-attachments/assets/dd355239-61fb-4185-9aae-cfc7376b4d7f)











            <<include your coding and its corressponding output screen shots here>>
# Result
          <<include your Result here>>
