## Pandas: Attributes and Methods for Data Analysis
NOTE: Maybe in future categorize these under specific headings.

### <ins>**Adding, Modifying Data, and Mapping**</ins>
**.fillna()**\
Fills in null values with specified value.

**.apply()**\
Allows the users to pass a function and apply it on every single value of the Pandas series.

**.map()**\
Modifies every individual cell in a series or column.It is used to map values from two series having one similar column. For mapping two series, the last column of the first should be the same as the index column of the second series, also the values should be unique.

**.applymap()**\
Updates every cell in the entire dataframe.  A method that applies a function that accepts and returns a scalar to every element of a DataFrame.

**.iterrows()**\
Iterates through each row and typicaly used in a for-loop.  It iterates over a Pandas DataFrame rows in the form of (index, series) pair. This function iterates over the data frame column, it will return a tuple with the column name and content in the form of a series.

**.dtypes**\
Gives the data types of the selected column.

**.info()**\
Displays various info about the dataset.

**.to_datetime()**\

**.describe()**\
Gives various statistical information about the numerical columns.

**.astype()**\
Used to change the data type of a series

### <ins>**Conditionals in Dataframes and Seris**</ins>

### <ins>**Binning**</ins>
**.contains()**\

**.qcut()**\
Bins all data into quartiles.  It divides the data so that each bin contains roughly equal data counts.

**.cut()**\
Bins all data based on equal intervals.  It divides the range so that each bin covers an equal interval.

### <ins>**Reshaping Data**</ins>




**pd.read_csv(file)**
**.head()**\
Displays top 5 rows

**.shape**\
Gives the dimensions of the dataset






**.isnull()**\
Gives the null values.

**.drop()**\
Drops a specified column. Usually includes 'inplace=True' to modify the current dataframe.

**.describe()**\
Gives various statistical information about the numerical columns.

**.value_counts()**\
Identifies the different categories in a feature as well as the count of values per category.


**.sample()**\
Chooses random values from the data frame.

**.nununique()**\
Finds number of unique values in our series or dataframe.

**.columns**\
Gets the names of all features/columns in our dataframe.

**.nsmallest()** and **.nlargest()**\
Used to obtain "n" number of rows from are data set which are lowers or highest.

**.groupby()**\
Enables grouping

**.agg()**\
Enables aggregations on the groups

**.get_group()**\
Selects a specific group.

**.loc()** and **.iloc()**\
Used in slicing data from the dataframe. Useful when you need to examine results not at the very beginning or ending of the dataframe.
**loc** - select by labels\
**iloc** - select by positions

**sort_index()** and **.sort_values()**\
Sorts dataframe by indices or values.

**.query()**\
Used to filter out dataframe per our conditions or requirements.

**.index()**\
Locates a row at the index position.

**.set_index()**\
Sets any column as the index of the dataframe

**.duplicated()**\
Finds all the duplicated rows in the dataset.

**.dropna()**\
Drops every row that includes at least one NA entry.  Be careful with this function because if there is any missing information in any of the columns for a given row, the entire row will be dropped.

**.drop_duplicates()**\
Drops the duplicate values in the dataset.

**.get_dummies()**\
Converts categorical features of the dat into dummy variables or indicator values.

**.select_dtypes()**\
Separates features according to specified data types.

**.concat()**\
Concatenates columns. By default, axis = 0, i.e.,row-wise concatenation,\
so if we set axis = 1, column-wise concatenation will be performed.

**.apply()**\
Allows us to apply a custom functon to every element of a particular series.

**.qcut()** and **.cut()**\
**qcut()** method ensures a more even distribution of the values inside each bin,\
so we can say it’s a better sampling.\
We just pass the no. of bins and then Pandas does the behind the scene job\
to decide how wide to make each bin.

**cut()** method is used to specifically\
define the bin edges and hence the distribution of values is not even across all the bins.\
There might be a situation when there is no item inside a particular bin,\
so we should be careful about that.

**.to_csv()**\
Saves the dataframe in a CSV file to a specied location.

