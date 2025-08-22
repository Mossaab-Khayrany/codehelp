# 🐍 Python + Pandas Cheatsheet for Data Analysis

This is a quick reference for commonly forgotten but **essential
commands** when working as a Data Analyst / Data Scientist in Python.

---

## 📦 Setup & Imports

```python
import pandas as pd
import numpy as np
```

---

## 📂 Reading Data

```python
# CSV / TXT with delimiter
df = pd.read_csv("file.csv", sep=";", encoding="latin-1")

# Excel
df = pd.read_excel("file.xlsx", sheet_name="Sheet1")

# JSON
df = pd.read_json("file.json")

# SQL
import sqlite3
conn = sqlite3.connect("db.sqlite")
df = pd.read_sql("SELECT * FROM table", conn)
```

---

## 👀 Display Settings

```python
pd.set_option("display.max_columns", None)   # show all columns
pd.set_option("display.max_rows", None)      # show all rows (careful!)
pd.set_option("display.max_colwidth", None)  # don't truncate text

# Reset to defaults
pd.reset_option("all")
```

---

## 🔎 Quick Exploration

```python
df.head()        # first 5 rows
df.tail()        # last 5 rows
df.shape         # (rows, cols)
df.info()        # column info + types
df.describe()    # summary stats (numeric)
df.sample(5)     # random 5 rows
```

---

## 🧹 Cleaning Data

```python
df.columns = df.columns.str.strip()     # strip spaces in column names
df.rename(columns={"old":"new"}, inplace=True)
df.dropna()                             # drop missing rows
df.fillna(0)                            # fill missing values
df.duplicated().sum()                   # count duplicates
df.drop_duplicates(inplace=True)
```

---

## 🔢 Selecting Data

```python
df["col"]                # select column
df[["col1", "col2"]]     # select multiple
df.loc[0]                # first row by label
df.iloc[0]               # first row by index
df.loc[df["age"] > 30]   # filter rows
df.query("age > 30")     # SQL-like filtering
```

---

## 📊 Aggregation & Grouping

```python
df["col"].value_counts()
df.groupby("category")["sales"].mean()
df.groupby(["cat", "subcat"]).size()
df.pivot_table(values="sales", index="region", columns="year", aggfunc="sum")
```

---

## 🔄 Merge / Join

```python
pd.merge(df1, df2, on="id", how="inner")
pd.concat([df1, df2], axis=0)   # stack rows
pd.concat([df1, df2], axis=1)   # stack columns
```

---

## 📈 Visualization (quick)

```python
import matplotlib.pyplot as plt

df["col"].hist()
df.plot(x="date", y="sales", kind="line")
plt.show()
```

---

## 💾 Save Data

```python
df.to_csv("output.csv", index=False)
df.to_excel("output.xlsx", index=False)
df.to_json("output.json", orient="records")
```

---

✅ This cheatsheet is meant to be **practical & minimal** --- the stuff
you forget but always need!
