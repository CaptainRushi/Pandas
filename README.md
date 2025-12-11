📊 Pandas – Full Documentation 

Pandas is a powerful, open-source Python library designed for high-performance data manipulation and analysis. It offers intuitive data structures, robust tools, and integration with the Python scientific ecosystem, making it a standard for data workflows.

📑 Table of Contents

Introduction

Key Features

Installation

Getting Started

Core Data Structures

Series

DataFrame

Data Input/Output

Data Selection & Indexing

Data Cleaning

Data Transformation

Grouping & Aggregation

Merging & Joining

Time Series

Common Operations

Performance

Use Cases

Resources

📘 Introduction

Pandas provides fast, flexible, and expressive data structures designed to make working with structured or tabular data intuitive. Its primary goal is to enable data cleaning, preparation, transformation, and analysis with minimal code.

⭐ Key Features

High-level Series (1-D) and DataFrame (2-D) data structures

Fast and efficient data manipulation

Built-in handling of missing data

Rich indexing and subsetting capabilities

Tools for reshaping, pivoting, merging, and joining

Support for time-series operations

Integration with NumPy, Matplotlib, and machine learning libraries

File reading/writing: CSV, Excel, JSON, HDF5, SQL, Parquet, and more

📦 Installation
pip install pandas


To upgrade:

pip install --upgrade pandas

🚀 Getting Started
import pandas as pd

df = pd.read_csv("data.csv")
print(df.head())

🏗 Core Data Structures
Series

A one-dimensional labeled array.

s = pd.Series([10, 20, 30], index=["a", "b", "c"])

DataFrame

A two-dimensional table with labeled axes.

data = {
    "name": ["John", "Sara", "Alex"],
    "age": [28, 22, 35]
}
df = pd.DataFrame(data)

📥 Data Input/Output
Read
pd.read_csv("file.csv")
pd.read_excel("file.xlsx")
pd.read_json("file.json")
pd.read_sql("SELECT * FROM table", connection)
pd.read_parquet("file.parquet")

Write
df.to_csv("output.csv", index=False)
df.to_excel("output.xlsx")
df.to_json("output.json")
df.to_parquet("output.parquet")

🎯 Data Selection & Indexing
df["column"]
df.loc["row_label"]
df.iloc[0]               # by index
df.loc[0:5, ["col1"]]   # range + specific columns
df[df["age"] > 25]      # conditional selection

🧹 Data Cleaning
df.dropna()
df.fillna(0)
df.duplicated()
df.drop_duplicates()
df.replace({"old": "new"})

🔧 Data Transformation
df["new"] = df["col"] * 2
df.rename(columns={"old": "new"})
df.sort_values("column")
df.apply(lambda x: x * 2)
df.astype(float)

📊 Grouping & Aggregation
df.groupby("category").sum()
df.groupby("category")["value"].mean()
df.pivot_table(values="sales", index="region", columns="year")

🔗 Merging & Joining
pd.merge(df1, df2, on="id")
pd.concat([df1, df2])
df.join(other_df, lsuffix='_l', rsuffix='_r')

🕒 Time Series

Pandas has rich time-series support:

df["date"] = pd.to_datetime(df["date"])
df.set_index("date", inplace=True)

df.resample("M").sum()
df.shift(1)
df.rolling(window=7).mean()

🧰 Common Operations
df.info()
df.describe()
df.columns
df.shape
df.isnull().sum()
df.value_counts()

⚡ Performance

Built on NumPy for optimized vectorized operations

Supports categorical data to reduce memory

Offers efficient joins, grouping, and filtering

Use df.astype(), categorical types, chunked reading, and .query() for optimization

📚 Use Cases

Data cleaning and preprocessing

Exploratory Data Analysis (EDA)

Machine learning pipelines

Financial and time-series analytics

Business intelligence

Big dataset manipulation

ETL workflows

🔗 Resources

Documentation: https://pandas.pydata.org/docs

GitHub Repo: https://github.com/pandas-dev/pandas

User Guide: Tutorials, examples, API reference
