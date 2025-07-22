# Cleaning Duplicates

Duplicate rows may cause your analysis to be skewed. Here's how to detect and remove them using Pandas.

## 🔍 Step 1: Detect Duplicates

```python
print(df.duplicated())         # Shows True for duplicate rows
print(df.duplicated().sum())   # Counts duplicate rows
```

## 🧹 Step 2: Remove Duplicates

```python
df.drop_duplicates(inplace=True)
```

## Optional: Keep the First or Last Entry

```python
df.drop_duplicates(keep='first', inplace=True)  # Keep first instance
df.drop_duplicates(keep='last', inplace=True)   # Keep last instance
```

## 💾 Save the Cleaned Data

```python
df.to_csv("cleaned_duplicates.csv", index=False)
```
