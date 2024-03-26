## Pandas: Attributes and Methods for Data Analysis

**pd.read_csv(file)**

**.head()**
Displays top 5 rows

**.shape**
Gives the dimensions of the dataset

**.info()**
Displays various info about the dataset.

**.to_datetime()**


**.isnull()**
Gives the null values.

**.drop()**
Drops a specified column. Usually includes 'inplace=True' to modify the current dataframe.

**.describe()**
Gives various statistical information about the numerical columns.

**.value_counts()**
Identifies the different categories in a feature as well as the count of values per category.

**.fillna()**
Fills in null values with specified value.

**.sample()**
Chooses random values from the data frame.

**.nununique()**
Finds number of unique values in our series or dataframe.

**.columns**
Gets the names of all features/columns in our dataframe.

**.nsmallest()** and **.nlargest()**
Used to obtain "n" number of rows from are data set which are lowers or highest.

**.groupby()**
Enables grouping

**.agg()**
Enables aggregations on the groups

**.get_group()**
Selects a specific group.

**.loc()** and **.iloc()**
Used in slicing data from the dataframe.\
**loc** - select by labels\
**iloc** - select by positions

**sort_index()** and **.sort_values()**
Sorts dataframe by indices or values.

**.query()**
Used to filter out dataframe per our conditions or requirements.

**.set_index()**
Sets any column as the index of the dataframe

**.duplicated()**
Finds all the duplicated rows in the dataset.

**.drop_duplicates()**
Drops the duplicate values in the dataset.

**.get_dummies()**
Converts categorical features of the dat into dummy variables or indicator values.

**.select_dtypes()**
Separates features according to specified data types.

**.concat()**
Concatenates columns. By default, axis = 0, i.e.,row-wise concatenation,\
so if we set axis = 1, column-wise concatenation will be performed.

**.apply()**
Allows us to apply a custom functon to every element of a particular series.

**.qcut()** and **.cut()**
**qcut()** method ensures a more even distribution of the values inside each bin,\
so we can say it’s a better sampling.\
We just pass the no. of bins and then Pandas does the behind the scene job\
to decide how wide to make each bin.

**cut()** method is used to specifically\
define the bin edges and hence the distribution of values is not even across all the bins.\
There might be a situation when there is no item inside a particular bin,\
so we should be careful about that.

**.to_csv()**
Saves the dataframe in a CSV file to a specied location.

