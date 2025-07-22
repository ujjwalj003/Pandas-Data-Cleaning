# Cleaning Empty Cells

Empty cells (or null values) can cause issues in data analysis. In this step, we handle them using Pandas.

## 🔍 Step 1: Identifying Empty Cells

```python
print(df.isnull())      # Shows True for empty cells
df.isnull().sum()       # Count of nulls in each column
```

## 🧹 Step 2: Handling Empty Cells

You can handle missing data in multiple ways:

### Option 1: Remove Rows with Empty Cells

```python
df.dropna(inplace=True)
```

### Option 2: Replace Empty Cells with a Specific Value

```python
df.fillna(130, inplace=True)  # Fills all NaNs with 130
```

### Option 3: Replace with Statistical Measures

```python
mean_val = df["Calories"].mean()
df["Calories"].fillna(mean_val, inplace=True)

median_val = df["Calories"].median()
df["Calories"].fillna(median_val, inplace=True)

mode_val = df["Calories"].mode()[0]
df["Calories"].fillna(mode_val, inplace=True)
```

## 💾 Save the Cleaned Data

```python
df.to_csv("cleaned_empty_cells.csv", index=False)
```
