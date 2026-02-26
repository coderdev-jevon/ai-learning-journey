[pandas tutorial](https://youtu.be/2uvysYbKdjM?si=WGQkiruFDP_nxSY6)

## Clone Git Hub Complete Tutorial
	1. copy url of the github tutorial
	2. go to CMD and change directory to your working folder
	3. type git clone url
	
## Set Virtual Environment (optional)
```bash
# Create virtual env in folder named venv
pyton -m venv venv
# Activate virtual env
venv\Scripts\Activate
# Install package
pip install -r requirements.txt
```

## Set up Visual Studio Code
	1. create ipynb (Interactive Python Notebook) to have the same utility as google colab
	2. try to run the code, select python environment of the venv you create
	3. there it is your ipynb notebook

## Features in IPYNB notebook
	1. use markdown cell to write type and Shift + Enter to run
	2. create new cell shortcut: press a to add cell above, press b to add cell below
	3. Shift + Enter -> run cell and go to below
	4. Ctrl + Enter -> run cell and stay
	5. Alt + Enter -> run cell and create new cell
	6. M -> change to markdown
	7. Y -> change to code
	8. DD -> delete cell
	9. Use md cell to hide cell by collapse (▾)

## Data Frames
#### Create Data Frames
```python
import pandas as pd

df = pd.DataFrame([[1,2,3], [4,5,6], [7,8,9]], columns=["A", "B", "C"], index=["X", "Y", "Z"]) #columns and index are optional
```

#### Print Out Data Frames
```python
df #look all of the rows
print(df) #look all of the rows
display(df) #look all of the rows

df.sample() #1 random row
df.sampe(10) #10 random rows
df.sample(10, random_state=1) #to make it deterministic when run
df.head() #look first 5 rows
df.head(2) #to look at the top two rows
df.tail() #look last 5 rows
df.tail(2) #to look at the bottom two rows

df.columns #to look at the columns header
df.index df.index.tolist() #to look the index

## use real label
df.loc[rows, columns]
df.loc[:, ["Day", "Units Sold"]] #use specific label for column
df.loc[rows] #can be [0,1,2], 0:3, [0,1,5], 5:, etc

## use index
df.iloc[:, [0,2]] #use index instead of label

# grab specific item
df.at[row, column] #use label
df.iat[row, column] #use index

df.info() #to look at info, int64 == 64 bits == 8 bytes
df.describe() #to look at descriptive statistics

df.unique() #to look at unique values
df.nunique() #how many unique values in each volumn
df['A'].unique() #go to column A and find unique values

df.shape #return the same of the dataframe
```

#### Modify Data Frames
```python
#CHANGE THE INDEX WILL CHANGE BEHAVIOR OF LOC AND ILOC
coffee.index = coffee["Day"] #to access column
coffee.index = conffee.Day #to access column

coffee.loc[1, "Units Sold"] = 10 # change the specific value read by loc and change the value to 10
```
## Read CSV Files and Explore the Data
	Pros of CSV Files: Easy to use, read, and understand
	Cons of CSV Files: Takes up a lot of space, three times of feather files, 9 times of parquet files, one point 5 times of xlsx files
	
```python
#READ CSV FILE
coffee = pd.read_csv("./warmup-data/coffee.csv")
	#OR
## From github, copy the raw data link, and change the url of the file with the url in website, easy!

#EXPLORE DATA
coffee.head()
```

## Read Parquet Files
```python
#READ PARQUEST FILE
results = pd.read_parquest("./data/results.parquet")

#EXPLORE DATA
results.head()
```

## Read Excel Files

> [!important]
[Clean Data Tutorial](https://www.youtube.com/live/oad9tVEsfI0?si=QeIp8AGcGqrYgzBK)

```python
#READ PARQUEST FILE
olympics_data = pd.read_excel("./data/olympics-data.xlsx", sheet_name="results") #sheet name is optional

#EXPLORE DATA
olympics_data.head()
```

## Convert File Extensions
```python
olympics_data.to_excel
olympics_data.to_parquet
olympics_data.to_csv
```

