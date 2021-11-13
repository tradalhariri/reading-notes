# pandas 

* pandas is a Python package which provide you with faster way to  work on data analysis .
* It uses tables (DataFrame)
* first you need to import it `import pandas as pd`
* `s = pd.Series([1, 3, 5, np.nan, 6, 8])` create a series of list with the dufault integer index
* you can create `DataFrame` by passing numpy array  with a datetime index and labeled columns
`dates = pd.date_range("20130101", periods=6)`
> DatetimeIndex(['2013-01-01', '2013-01-02', '2013-01-03', '2013-01-04',
               '2013-01-05', '2013-01-06'],
              dtype='datetime64[ns]', freq='D')
`df = pd.DataFrame(np.random.randn(6, 4), index=dates, columns=list("ABCD"))`
* you can create dataframe by passing a dictionary object.

```python
df2 = pd.DataFrame(
    {
        "A": 1.0,
        "B": pd.Timestamp("20130102"),
        "C": pd.Series(1, index=list(range(4)), dtype="float32"),
        "D": np.array([3] * 4, dtype="int32"),
        "E": pd.Categorical(["test", "train", "test", "train"]),
        "F": "foo",
    }
)

```
* the columns in dataframes may have different types.
* `DataFrame.to_numpy()` convert data to numpy representation.

* `data = pd.read_csv('my_file.csv', sep=';', encoding='latin-1', nrows=1000, skiprows=[2,5])` 

> sep means separator. If you’re working with French data, csv separator in Excel is “;” so you need to explicit it. Encoding is set to “latin-1” to read French characters. nrows=1000 means reading the first 1000 rows. skiprows=[2,5] means you will remove the 2nd and 5th row when reading the file

* if you want to write data `data.to_csv('my_new_file.csv', index=None)`
> index=None will simply write the data as it is. If you don’t write index=None, you’ll get an additional first column of 1,2,3, … until the last row.

* `data.shape` gives you the number of rows and columns.
* `data.describe()` gives you the basic statistics info.
* ` data.head(3)` returns the first three rows.
* `data.tail(3)` returns the last three rows.
* `data.loc[8]` return the 9th row
* `data.loc[8, 'column_1']` return the value in 9th row and `column_1` column
* `data.loc[range(4,6)]` return subset of rows (row 5th and 6th ) 
* you can use logical operators to retrieve specific data.

```python
data[(data['column_1']=='french') & (data['year_born']==1990)]
```
retrieve rows that have `column_1` equal `french` and `year_born` equal `1990`
* you can use `isin` instaed of writing multiple ors on the same column. `data[data['column_1'].isin(['french', 'english'])]`
* matplotlib package is a package that can plot diagrams for you data and it is usable directly inside pandas. `data['column_numerical'].plot()`
![](https://miro.medium.com/max/489/1*QyYuLym-PSTQk_3MYt81VA.png)

* you can change multiple rows in one line `data.loc[data['column_1']=='french', 'column_1'] = 'French'`
* you can count the data in each column. `data.loc[data['column_1']=='french', 'column_1'] = 'French'`


# References
[10 minutes to pandas](https://pandas.pydata.org/pandas-docs/stable/user_guide/10min.html#selection)
[Be a more efficient data scientist, master pandas with this guide](https://towardsdatascience.com/be-a-more-efficient-data-scientist-today-master-pandas-with-this-guide-ea362d27386)