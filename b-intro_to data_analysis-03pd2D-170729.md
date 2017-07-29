## 2D Array and Dataframe
* 2D Array 每个元素必须类型相同
* Dataframe 可以有列名 每列的元素类型可以不同
`pd.DataFrame({ key:value})` key 为列名 value 为每列的内容

## Accessing Data in a DataFrame
df[’col’].......................Get column by name
 df.iloc[i] ...................... Get row by position 
df.loc[x] .......................... Get row by index 
df.iloc[i, j]...............Get element by position 
df.loc[x, y]...................Get element by index 
df.values......................Get 2D NumPy array

## Loading Data into a DataFrame
```python
df = pd.read_csv(filename)
df.head( )
df.describe( )
```

## correlation
Pearson's r
```python
def correlation(x, y):
    std_x = (x - x.mean()) / x.std(ddof=0)
    std_y = (y - y.mean()) / y.std(ddof=0)
    
    return (std_x * std_y).mean()
```
自己用函数实现 皮尔森r
`correlation(x, y)` 这是 Numpy 自带的 相关性计算函数

