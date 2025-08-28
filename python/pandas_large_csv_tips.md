# Handling Large CSVs in Pandas

Here are some practical tricks to make working with large CSV files efficient in pandas:

---

## 1. Read in chunks

If you don’t need the full dataset at once, use `chunksize` to process data in pieces.

```python
import pandas as pd

chunksize = 100_000  # adjust as needed
totals = 0

for chunk in pd.read_csv("yourfile.csv", sep=";", encoding="utf-8", chunksize=chunksize):
    totals += chunk["P20_POP"].sum()

print("Total population:", totals)
```

---

## 2. Specify `dtype` for columns

By default, pandas guesses datatypes → can waste memory. You can save memory by explicitly defining types:

```python
dtypes = {
    "IRIS": "string",
    "COM": "string",
    "TYP_IRIS": "category",  # few unique values
    "P20_POP": "int32",
}

data = pd.read_csv("yourfile.csv", sep=";", encoding="utf-8", dtype=dtypes)
```

---

## 3. Use `usecols` to only read needed columns

If you don’t need all 70+ columns, specify only the ones you need:

```python
cols = ["IRIS", "COM", "P20_POP", "P20_POP_FR", "P20_POP_ETR"]
data = pd.read_csv("yourfile.csv", sep=";", encoding="utf-8", usecols=cols)
```

---

## 4. Convert wide → long format

INSEE-style CSVs often have many columns like `P20_POP0014`, `P20_POP1529`, …  
You can reshape into a tidy format:

```python
pop_cols = [c for c in data.columns if c.startswith("P20_POP")]
tidy = data.melt(
    id_vars=["IRIS", "COM"],
    value_vars=pop_cols,
    var_name="age_group",
    value_name="population"
)
```

This makes filtering, grouping, and plotting easier.

---

## 5. Save a **Parquet** copy

After cleaning, save as **Parquet** (binary columnar format).  
It’s smaller and much faster to reload than CSV:

```python
data.to_parquet("population2020.parquet", index=False)
# Next time:
df = pd.read_parquet("population2020.parquet")
```

On average → loads **10x faster** than CSV.

---

## Extra: Check memory usage

To see where optimizations are possible:

```python
data.info(memory_usage="deep")
```

This will show memory usage per column and total usage.

---

✅ With these tricks, you can handle 50 MB+ CSV files comfortably and prepare your workflow for even larger datasets.
