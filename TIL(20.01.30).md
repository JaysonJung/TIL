# TIL(20.01.30)

- Backward Elimination

  - An approach of stepwise regression
  - It involves starting with all candidate variables, testing the deletion of each variable using a chosen model fit criterion, deleting the variable (if any) whose loss gives the most statistically insignificant deterioration of the model fit, and repeating this process until no further variables can be deleted without a statistically significant loss of fit.
  - [Wikipedia][Ref]:https://en.wikipedia.org/wiki/Stepwise_regression

  

- Numpy where function

  ```python
  #Example of filtering values by condition
  >>> a = np.arange(10)
  >>> a
  array([0, 1, 2, 3, 4, 5, 6, 7, 8, 9])
  >>> np.where(a < 5, a, 10*a)
  array([ 0,  1,  2,  3,  4, 50, 60, 70, 80, 90])
  ```

  

# TIL(20.01.31)

- Select specific columns except some by column's indices in pandas

- ```python
  #Get name of columns
  columns_name=df.columns[columns_index_list].values
  #Get columns except some
  df.loc[:,~df.columns.isin(columns_name)]
  ```

- Select specific rows by condition

- ```python
  #Get index values which have value 1(condition) from label dataframe
  label_index_values=df_label[df_label.values==1].index.values
  ```

- 

