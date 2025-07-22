# Cleaning Wrong Format

Formatting issues (like dates as strings or inconsistent types) can cause parsing errors. Here's how to fix them.

## 🔍 Step 1: Identifying Format Issues

```python
print(df.dtypes)   # Check the data types of all columns
```

## 🧹 Step 2: Convert to Proper Format

### Convert "Date" to datetime

```python
df["Date"] = pd.to_datetime(df["Date"], errors='coerce')
```

This will convert valid dates and turn incorrect formats into NaT (Not a Time).

### Optional: Drop rows with NaT in "Date"

```python
df.dropna(subset=["Date"], inplace=True)
```

## 💾 Save the Cleaned Data

```python
df.to_csv("cleaned_wrong_format.csv", index=False)
```
