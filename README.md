Here’s how to import the Pandas library and load it into the dataset:



Datasets loaded successfully!

1. Head and Tail
Once we read a dataset into a pandas data frame, we want to take a look at it to get an overview. The simplest way is to display some rows. Head and tail allow us to display rows from the top or the bottom of the data frame, respectively.





5 rows are displayed by default but we can adjust it just by passing the number of rows we’d like to display.

2. DataFrame.info( )
Pandas dataframe.info() function is used to get a concise summary of the dataframe. It comes really handy when doing exploratory analysis of the data. To get a quick overview of the dataset we use the dataframe.info() function.


3. Dtypes
We need to have the values stored in an appropriate data type. Otherwise, we may encounter errors. For large datasets, memory usage is greatly affected by correct data type selection. For example, the “categorical” data type is more appropriate than the “object” data type for categorical data especially when the number of categories is much less than the number of rows.

Dtypes show the data type of each column.


4. Shape and Size
The shape can be used on numpy arrays, pandas series, and data frames. It shows the number of dimensions as well as the size of each dimension.

Since data frames are two-dimensional, what shape returns is the number of rows and columns. It is a measure of how much data we have and a key input to the data analysis process.

Furthermore, the ratio of rows and columns is very important when designing and implementing a machine learning model. If we do not have enough observations (rows) with respect to features (columns), we may need to apply some pre-processing techniques such as dimensional reduction or feature extraction.


Size, as the name suggests, returns the size of a dataframe which is the number of rows multiplied by the number of columns.


5. describe( )
If there’s one thing you do over and over again in the process of exploratory data analysis — that’s performing a statistical summary for every (or almost every) attribute.

It would be a quite tedious process without the right tools — but thankfully Pandas is here to do the heavy lifting for you. The describe() method will do a quick statistical summary for every numerical column, as shown below:


Now I’m using the transpose operator to switch from columns to rows, and vice-versa.


6. Sample
The sample method allows you to select values randomly from a Series or DataFrame. It is useful when we want to select a random sample from a distribution.


7. Identifying Missing Values Isnull
Handling missing values is a critical step to build a robust data analysis process. The missing values should be a top priority since they have a significant effect on the accuracy of any analysis.


8. Isna
Isna function returns a dataframe filled with boolean values with true indicating missing values.


9. Identifying Missing Values Sum
Let’s first compute the total number of missing values in the data frame. You can calculate the number of missing values in each column by df.isnull().sum()


10. Nunique
Nunique counts the number of unique entries over columns or rows. It is very useful in categorical features, especially in cases where we do not know the number of categories beforehand. Let’s take a look at our initial dataframe:


11.Index( ) and column( )
index() is an inbuilt function in Python, which searches for a given element from the start of the list and returns the lowest index where the element appears.


Column( )

12.Memory_usage
Memory_usage() returns how much memory each column uses in bytes. It is useful especially when we work with large data frames. Consider the following dataframe with 1 million rows.


13. nsmallest() and nlargest()
I’m guessing there’s no doubt about the purposes of these two methods after just reading their names, but nevertheless, they can prove to be worthy in the process of exploratory data analysis.

Let’s see how we’d go about finding the 5 observations with the smallest value


Let’s see how we’d go about finding the 5 observations with the Largest value.


14. Loc and iloc
Loc and iloc are used to select rows and columns.

loc: select by labels
iloc: select by positions
loc is used to select data by the label. The labels of columns are the column names. We need to be careful about row labels. If we do not assign any specific indices, pandas created an integer index by default. Thus, the row labels are integers starting from 0 and going up. The row positions that are used with iloc are also integers starting from 0.

Selecting the first 6 rows and 2 columns with loc:


Selecting the first 4 rows and first 6 columns with iloc:


15. Slicing
Slicing Rows and Columns using labels. You can select a range of rows or columns using labels or by position. To slice..


16. Groupby
pandas groupby function is a great tool in exploring the data. It makes it easier to unveil the underlying relationships among variables. The figure below shows an overview of what the groupby function does.


17. Sorting
Using the sort_index() method, by passing the axis arguments and the order of sorting, DataFrame can be sorted. By default, sorting is done on row labels in ascending order. Order of Sorting. By passing the Boolean value to ascending parameter, the order of the sorting can be controlled.


sorting by values


18.Dropna
The dropna() function is used to remove a row or a column from a dataframe that has NaN or no values in it.


19. Query
We sometimes need to filter a dataframe based on a condition or apply a mask to get certain values. One easy way to filter a dataframe is the query function. Let’s first create a sample dataframe.


20. Insert
When we want to add a new column to a dataframe, it is added at the end by default. However, pandas offer the option to add a new column in any position using the insert function.

We need to specify the position by passing an index as the first argument. This value must be an integer. Column indices start from zero just like row indices. The second argument is the column name and the third argument is the object that includes values that can be Series or an array-like object.


