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
```
d.isnull().sum()
```

![image](https://github.com/user-attachments/assets/f5b6edae-8123-4567-9376-013d2e257162)
```
d.isnull().any()
```

![image](https://github.com/user-attachments/assets/fbf32a80-c9db-4f12-b734-af9053af105f)
```
d.dropna()
```

![image](https://github.com/user-attachments/assets/a364d810-886e-4580-8918-c54acbef1746)
```
d.fillna(0)
```

![image](https://github.com/user-attachments/assets/a04f2c40-6fc7-4244-a537-e6e4118e424a)
```
d.fillna(method = 'bfill')
```

![image](https://github.com/user-attachments/assets/7ccbc364-4be1-46b7-b448-fd910e4b5e50)
```
df_dropped=d.dropna()
df_dropped
```

![image](https://github.com/user-attachments/assets/1e84aa94-603c-4ac4-8bf7-8ec2eefef5ca)
```
d.fillna({'GENDER':'MALE','NAME':'SRI','ADDRESS':'POONAMALEE','M1':98,'M2':87,'M3':76,'M4':92,'TOTAL':305,'AVG':89.999999})
```

![image](https://github.com/user-attachments/assets/bbd416fb-1bd6-47b1-96f3-ea2e87ae7444)
```
ir=pd.read_csv("/content/iris.csv")
ir
```

![image](https://github.com/user-attachments/assets/e90b1e98-d709-4daa-9742-f5ece75fd82f)
```
ir.describe()
```

![image](https://github.com/user-attachments/assets/dd355239-61fb-4185-9aae-cfc7376b4d7f)
```
import seaborn as sns
sns.boxplot(x='sepal_width',data=ir)
```

![image](https://github.com/user-attachments/assets/e898d9f6-d27e-4c06-95a3-e81b2db0e58f)
```
c1=ir.sepal_width.quantile(0.25)
c3=ir.sepal_width.quantile(0.75)
iq=c3-c1
print(c3)
```

![image](https://github.com/user-attachments/assets/4a1e4872-235c-4e6f-9fb3-58660c023818)
```
rid=ir[((ir.sepal_width<(c1-1.5*iq))|(ir.sepal_width>(c3+1.5*iq)))]
rid['sepal_width']
```

![image](https://github.com/user-attachments/assets/6256c3e7-4a88-4a80-947e-64a035c0ac22)
```
delid=ir[~((ir.sepal_width<(c1-1.5*iq))|(ir.sepal_width>(c3+1.5*iq)))]
delid
```

![image](https://github.com/user-attachments/assets/f754d703-c37e-426e-8ca1-bbb8d8adeb99)
```
sns.boxplot(x='sepal_width',data=delid)
```

![image](https://github.com/user-attachments/assets/312ac8b1-6331-443c-b0de-3839c105e5ff)
```
import matplotlib.pyplot as plt
import numpy as np
import scipy.stats as stats
dataset=pd.read_csv("heights.csv")
dataset
```

![image](https://github.com/user-attachments/assets/bf51fd99-fff3-4867-aaa7-1550ce3f255f)
```
df = pd.read_csv("heights.csv")
q1 = df['height'].quantile(0.25)
q2 = df['height'].quantile(0.5)
q3 = df['height'].quantile(0.75)
iqr = q3-q1
iqr
```

![image](https://github.com/user-attachments/assets/d7783cf4-0822-48ad-be41-3e41296c57fe)
```
low = q1 - 1.5*iqr
low
```

![image](https://github.com/user-attachments/assets/68ba2c12-7ce9-47a5-9174-40a076e18229)
```
high = q3 + 1.5*iqr
high
```

![image](https://github.com/user-attachments/assets/31f50c25-5f04-4cf8-bda2-a640cf491bf4)
```
df1 = df[((df['height'] >=low)& (df['height'] <=high))]
df1
```

![image](https://github.com/user-attachments/assets/3ad7ec0d-e874-4f94-8b28-05397769e451)
```
z = np.abs(stats.zscore(df['height']))
z
```

![image](https://github.com/user-attachments/assets/e424b380-dcb4-4d53-adc8-42d919222b8e)
```
df1 = df[z<3]
df1
```

![image](https://github.com/user-attachments/assets/5d29e2a8-0a70-459b-ac90-9feac7d2ca82)





















            
# Result
          Thus we have cleaned the data and removed the outliers by detection using IQR and Z-score method.
