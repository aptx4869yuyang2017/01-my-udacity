## 2D Array and Dataframe
* 2D Array 每个元素必须类型相同
* Dataframe 可以有列名 每列的元素类型可以不同
`pd.DataFrame({ key:value})` key 为列名 value 为每列的内容

## Accessing Data in a DataFrame
* `df[’col’]` 
* `df.iloc[i]`  Get row by position   
* `df.loc[x]   df[x]` 这个应该也是根据 index 来索引的
* `df.iloc[i, j]`...............Get element by position 
* `df.loc[x, y]`...................Get element by index 
* `df.values`......................Get 2D     **NumPy array 'numpy.ndarray' object is not callable** **不能加括号**


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

## Pandas Axis Name
axis = 0 竖向计算 默认值
axis = 1 水平计算 
忘记用字符串的标记方式吧  又难记 又难写 

### Pandas Verctorized Operation
`df.shift( )` 向坐标方向移动位置

### DataFrame applymap( ) vs apply( ) 

`df.applymap(function)`  这个是应用在每个元素上
  
`df.apply(function)`  这个是应用在每个 column 上面，因为有时候 function 的映射关系是依存于整个 column 的。例如学生成绩是根据排名来分类的例子
## 加减乘除的 axis=1
* df.add(df_1, axis = 1)
* df.sub(df_, axis = 1)

