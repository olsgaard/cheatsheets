# Pandas
Pandas for R programmers. Pandas version on left, R equivelant on the right.

## Apply function f to entire dataframe / pipe

```python

df.pipe(f, arg1) 	# df %>% f(arg1)

```

## Selecting columns and filtering for rows

Selecting rows and columns using `.loc` and `[]`
```python

# Select both rows and columns
df.loc[[rows], [columns]]

# Selecting columns only
df[[cols]]

df.loc[:, [cols]]	# df %>% select(cols)

# Filtering rows
df[[n_rows_of_bools]]

# This filters by the `index`, which may or may not be 0..n, 
# it could be named rows, or have missing numbers
df.loc[row]			# df %>% filter(rows)

# Filters by row order, numbered from 0:n
# Confusingly, the `index` is usually, but not always the same
df.iloc[row_numbers]
df.iloc[i:j]
```

## Mutating / assigning

```python
df.assign(col = new_value)	# df %>% mutate(col = new_value)
```


## Apply, map, transform

```python
# Apply a single function to each column (any axis) - allows aggregation
df.apply(lambda series: f(series))	# df %>% mutate(across(everything()), f)

# Apply a function to each cell
df.applymap(lambda x: f(x))

# Apply a function to entire dataframe
df.pipe(lambda df: f(df))

# Apply multiple functions to each column, potentially creating a multi-index result. Does not allow aggregation
df.transform([lambda col: f(col), f2, f3 ...])
df.transform([lambda row: f(row), f2, f3 ...], axis=1)


# Note that when transforming a subset of columns, the rest are discarded
(pd.DataFrame({col: range(10) for col in "ABC"})
    .transform({"A": "square"}))
# -> 1-column dataframe
```
See also
	- https://stackoverflow.com/questions/19798153/difference-between-map-applymap-and-apply


## Unique rows / drop duplicates

In pandas, you should not think of this as "selecting unique rows / values", but as "dropping duplicated rows / values"


```python

unique_df = df.drop_duplicates()

unique_series = df["col"].drop_duplicates()
unique_numpy_array = df["col"].unique() # This is the worst - some rows might change dtype!

```

## If else

```python
df.assign(
    col1 = lambda x: x.col1.where(x.col1 < 0, 0)
)
```

# Aggregation recipe

