## pandas 读取 CSV
* 速度快。。
```python
import pandas as pd

filename = '.name'
df = pd.read_csv(filename)
```
## 两种数据结构对比
* panda Series 建立在Numpy 的Array 基础之上，特性更多
* Numpy Array 简单，是学习和理解 Series 的基础
## Series
* 与列表相同的特性
    * 索引 `a[0]`
    * 切片 `a[1: 3]`
    * 遍历 `for i in a: pass`
* 与列表不同的特性
    * 必须是相同数据类型
    * 有丰富的方法：`a.mean( )` `a.std( )`
    * 多维的特性
## Series 的向量操作
* 加减乘除
* 逻辑运算
* 比较运算
实例 standardizing Data
```python
def standarize_data(values):
    standardized_values = (values - values.mean()) / values.std( )
    return standarized_data
```
##  NumPy Index Arrays
```python
a = [1 2 3 4 5]
b = [False False True True True]
a[b] = [3 4 5]
```

## Array 切片的特殊存放机制
* array 的切片只是又找了一个容器，装的还是原来的东西
## Pandas 索引
`Series.iloc[0]` 推荐的索引方式

## Pandas Series Index
* NumPy  arrays 是加强版的 python 列表
* Pandas Series 是 python 列表和字典的 结合
```python
life_expectancy = pd.Series([74, 75 76, 77, 78],
                                                 index=["A", "B", "C", "D", "E"])
 
```
`max_index = Series.argmax( )`  最大值的 index
`max_value = Series.loc[max]`  最大值的值
`Series.idxmax( )` 
##  Pandas Series Add base on Index
* 以 index 为模式进行 Series 加法
* 三种模式的 Series 加法 
```python
s1 = pd.Series([1, 2, 3, 4], index = ['a', 'b', 'c', 'd'])
s2 = pd.Series([10, 20, 30, 40], index = ['c', 'd', 'e', 'f'])
```
    * `sum_result = s1 + s2` 普通模式
    * `sum_result.dropna( )` 去除NA模式
    * `s1.add(s2, fill_value=0)` 加 0 模式
## Series .apply( )  method

apply 中**传入的是函数**   不是函数的调用 就是不加括号
```python
def add3(a ):
    return a + 3
s1 = pd.Series([1, 2, 3, 4])
s1.apply(add3) # 注意要传入的是函数 而不是函数调用
```
## Plot

`Series.plot(kind="")` 里面可以选择图像的形式

```python
%matplotlib inline # 在 ipython 中显示图像
plot_result.plot(kind='hist')
```
