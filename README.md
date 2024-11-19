# EXNO-6-DS-DATA VISUALIZATION USING SEABORN LIBRARY

## AIM:
  To Perform Data Visualization using seaborn python library for the given datas.

## EXPLANATION:
Data visualization is the graphical representation of information and data. By using visual elements like charts, graphs, and maps, data visualization tools provide an accessible way to see and understand trends, outliers, and patterns in data.

## ALGORITHM:
STEP 1:Include the necessary Library.

STEP 2:Read the given Data.

STEP 3:Apply data visualization techniques to identify the patterns of the data.

STEP 4:Apply the various data visualization tools wherever necessary.

STEP 5:Include Necessary parameters in each functions.

## CODING AND OUTPUT:

## LINE PLOT:
```PYTHON
import pandas as pd
import numpy as np
import seaborn as sns
import matplotlib.pyplot as plt

x = [1, 2, 3, 4, 5]
y = [3, 6, 2, 7, 1]

sns.lineplot(x=x,y=y)
```

### OUTPUT:
![alt text](screenshot/image.png)

### SHOW THE DATASET VALUES:
```
df=sns.load_dataset('tips')
df
```

### OUTPUT:
![alt text](screenshot/image-1.png)

```PYTHON
sns.lineplot(x='total_bill',y='tip',data=df,hue='sex',linestyle='solid',legend='auto')
```

### OUTPUT:
![alt text](screenshot/image-2.png)

## MULTI-LINE PLOT:
```PYTHON
x = [1, 2, 3, 4, 5]
y1 = [3, 5, 2, 6, 1]
y2 = [1, 6, 4, 3, 8]
y3 = [5, 2, 7, 1, 4]

sns.lineplot(x=x,y=y1)
sns.lineplot(x=x,y=y2)
sns.lineplot(x=x,y=y3)

plt.title("Multi-Line Plot")
plt.xlabel('X label')
plt.ylabel('Y label')
```

### OUTPUT:
![alt text](screenshot/image-3.png)

## BAR PLOT:
```PYTHON
import seaborn as sns
import matplotlib.pyplot as plt

tips = sns.load_dataset('tips')

avg_total_bill=tips.groupby('day')['total_bill'].mean()
avg_tip=tips.groupby('day')['tip'].mean()

plt.figure(figsize=(8,6))
p1=plt.bar(avg_total_bill.index,avg_total_bill,label='Total Bill')
p2=plt.bar(avg_tip.index,avg_tip,bottom=avg_total_bill,label='Tip')

plt.xlabel('Day of the Week')
plt.ylabel('Amount')
plt.title('Average Total Bill and Tip by Day')
plt.legend()
```

### OUTPUT:
![alt text](screenshot/image-4.png)

### CREATE A STACKED BAR PLOT:
```PYTHON
avg_total_bill=tips.groupby('time')['total_bill'].mean()
avg_tip=tips.groupby('time')['tip'].mean()

p1=plt.bar(avg_total_bill.index,avg_total_bill,label='Total Bill',width=0.4)
p2=plt.bar(avg_tip.index,avg_tip,bottom=avg_total_bill,label='Tip',width=0.4)

plt.xlabel('Time of Day')
plt.ylabel('Amount')
plt.title('Average Total Bill and Tip by Day')
plt.legend()
```
### OUTPUT:
![alt text](screenshot/image-5.png)

```PYTHON
import seaborn as sns
dt=sns.load_dataset('tips')

sns.barplot(x='day',y='total_bill',hue='sex',data=dt,palette='Set1')

plt.xlabel('Day of the week')
plt.ylabel('total Bill')
plt.title('Total Bill by Day and Gender')
```
### OUTPUT:
![alt text](screenshot/image-6.png)

```PYTHON
import seaborn as sns
dr=sns.load_dataset('tips')

sns.histplot(data=dr,x='total_bill',hue='sex',kde=True)

plt.xlabel('Day of the week')
plt.ylabel('total Bill')
plt.title('Total Bill by Day and Gender')
```
### OUTPUT:
![alt text](screenshot/image-7.png)

## USING TIPS DATASET IMPLEMENT SCATTER PLOT OF THE TOTAL BILL VS TIP AMOUNT:
```PYTHON
import seaborn as sns

tips=sns.load_dataset('tips')

sns.scatterplot(x='total_bill',y='tip',hue='sex',data=tips)

plt.xlabel('Total Bill')
plt.ylabel('Tip Amount')
plt.title('Scatter Plot of Total Bill vs. Tip Amount')
```
### OUTPUT:
![alt text](screenshot/image-8.png)

### VIOLIN PLOT:
```PYTHON
sns.violinplot(x='day',y='total_bill',hue='smoker',data=tips,linewidth=2,width=0.6)

plt.xlabel("Day of the week")
plt.ylabel("Total Bill")
plt.title("Violin Pot of Total Bill by Day and Smoker status")
```

### OUTPUT:
![alt text](screenshot/image-9.png)

```PYTHON
import seaborn as sns

sns.set_theme(style='whitegrid')
tip = sns.load_dataset('tips')
sns.violinplot(x='day', y='tip', data=tip, palette="hsv")
```

### OUTPUT:
![alt text](screenshot/image-10.png)

```python
sns.violinplot(x='day', y='tip', hue='sex', data=tip, palette='Set2', split=True, scale='count', inner='quartile', bw=0.5, linewidth=1)
```

### OUTPUT:
![alt text](screenshot/image-13.png)

```PYTHON
import seaborn as sns

sns.set_theme(style='whitegrid')
tip = sns.load_dataset('tips')
sns.violinplot(x='tip', y='day', data=tip, palette="Spectral")
```
### OUTPUT:
![alt text](screenshot/image-11.png)

```PYTHON
sns.set_theme(style='whitegrid')
tip=sns.load_dataset('tips')
sns.violinplot(x=tip["total_bill"])
```

### OUTPUT:
![alt text](screenshot/image-12.png)

### BOX PLOT:
```PYTHON
import seaborn as sns
import pandas as pd
tips = sns.load_dataset('tips')
sns.boxplot(x='day', y='total_bill', hue='sex', data=tips, palette='dark')
```

### OUTPUT:
![alt text](screenshot/image-14.png)

```python
sns.boxplot(x='day',y='total_bill',hue='smoker',data=tips,linewidth=2,width=0.6,boxprops={"facecolor":"green","edgecolor":"yellow"},whiskerprops={"color":"green","linestyle":"--","linewidth":1.5},capprops={"color":"black","linestyle":"--","linewidth":1.5})
```

### OUTPUT:
![alt text](screenshot/image-15.png)

### KDE PLOT:
```PYTHON
sns.kdeplot(data=tips,x='total_bill',hue='time',multiple='fill',linewidth=3,palette='dark',alpha=0.8)
```

### OUTPUT:
![alt text](screenshot/image-16.png)

```PYTHON
sns.kdeplot(data=tips,x='total_bill',hue='time',multiple='layer',linewidth=3,palette='crest',alpha=0.8)
```

### OUTPUT:
![alt text](screenshot/image-17.png)

```PYTHON
sns.kdeplot(data=tips,x='total_bill',hue='time',multiple='stack', linewidth=3,palette='colorblind',alpha=0.8)
```

### OUTPUT:
![alt text](screenshot/image-18.png)

```PYTHON
sns.kdeplot(data=tips, x='total_bill', hue='time', fill=True, alpha=0.4, palette='bright')
sns.rugplot(data=tips, x='total_bill', color='black', height=0.1)
plt.title('KDE Plot with Rug')
plt.show()
```

### OUTPUT:
![alt text](screenshot/image-19.png)

```PYTHON
data=np.random.randint(low=1,high=100,size=(10,10))
print(data)
```
### OUTPUT:
![alt text](screenshot/image-20.png)

```PYTHON
hm=sns.heatmap(data=data,annot=True)
```

### OUTPUT:
![alt text](screenshot/image-21.png)

```PYTHON
sns.heatmap(data=data)
```

### OUTPUT:
![alt text](screenshot/image-22.png)

```python
custom_palette = sns.color_palette("coolwarm", as_cmap=True)
hm = sns.heatmap(data=data, annot=True, cmap=custom_palette)
plt.title('Heatmap with Custom Coolwarm Palette')
plt.show()
```

### OUTPUT:
![alt text](screenshot/image-23.png)

```PYTHON
hm = sns.heatmap(data=data, annot=True, annot_kws={"size": 10}, cmap='Reds')
plt.title('Heatmap with Custom Annotation Font Size')
plt.show()
```

### OUTPUT:
![alt text](screenshot/image-24.png)

```PYTHON
tips=sns.load_dataset("tips")
numeric_cols=tips.select_dtypes(include=np.number).columns
corr=tips[numeric_cols].corr()
sns.heatmap(corr,annot=True,cmap="plasma",linewidth=0.5)
```

### OUTPUT:
![alt text](screenshot/image-25.png)

## RESULT:
Thus the Seaborn Libraries have used and done successfully.
