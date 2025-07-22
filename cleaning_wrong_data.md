# Cleaning Wrong Data

Wrong data includes values that are invalid or illogical based on domain knowledge.

## 🔍 Step 1: Identify Wrong Data

Example: Duration over 300 minutes is likely incorrect.

```python
print(df[df["Duration"] > 300])
```

## 🧹 Step 2: Handle the Wrong Data

### Option 1: Replace Invalid Values

```python
df.loc[df["Duration"] > 300, "Duration"] = df["Duration"].median()
```

### Option 2: Remove Rows with Wrong Data

```python
df = df[df["Duration"] <= 300]
```

You can apply similar filters to Pulse, Calories, or other numeric values.

## 💾 Save the Cleaned Data

```python
df.to_csv("cleaned_wrong_data.csv", index=False)
```
