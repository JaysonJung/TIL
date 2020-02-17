# TIL(20.2.17)

- PyCox 보던중 DataFrame 처리 방법이 신기해서 보게되었다

```python
df_target.assign(expg=np.exp(self.predict(input, batch_size, True, eval_, num_workers=num_workers)))
                .groupby(self.duration_col)
                .agg({'expg': 'sum', self.event_col: 'sum'})
                .sort_index(ascending=False)
                .assign(expg=lambda x: x['expg'].cumsum())
                .pipe(lambda x: x[self.event_col]/x['expg'])
                .fillna(0.)
                .iloc[::-1]
                .loc[lambda x: x.index <= max_duration]
                .rename('baseline_hazards')
##Pandas Funcitons##
#assign : Assign new columns to a DataFrame. Returns a new object with all original columns in addition to new ones. Existing columns that are re-assigned will be overwritten.

#agg : Aggregate using one or more operations over the specified axis.

#sort_index : Sort Series by index labels.

#pipe : Apply func(self, *args, **kwargs).
```



