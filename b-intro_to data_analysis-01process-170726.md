b-intro_to data_analysis-170726


* CVS 转换成 Python 数据结构可以有两种形式：
    * 列表
    * 字典
```python
csv =[
 ['a1', 'a2', 'a3'],
['b1', 'b2', 'b3']
]
csv = [
{"name1":"a1", "name2":"a2"},
["name1":"b1", "name2":"b2"]
]
```
* 使用 uniccodecsv 解析 CSV
```python
import unicodecsv

def read_csv(filename):
    with open(filename, 'rb') as f:
        reader = unicodecsv.DictReader(f)
        return list(reader)
```
* 一些常见的格式转换
**转换日期**
```python
from datetime import datetime as dt
# Takes a date as a string, and returns a Python datetime object. 
# If there is no date given, returns None
def parse_date(date):
    if date == '':
        return None
    else:
        return dt.strptime(date, '%Y-%m-%d')
    
dict[key] = parse_date(dict[key])
```
**转换为整数**
```python
def parse_maybe_int(i):
    if i == '':
        return None
    else:
        return int(i)

dict[key] = parse_maybe_itn(dict[key])
```
**转换为布尔值**
```python
dict[key] = dict[key] == 'True'
```

* 利用集合 Set( ) 特性，过滤重复信息
```python
unique_enrolled_students = set()
print type(unique_enrolled_students)
for enrollment in enrollments:
    unique_enrolled_students.add(enrollment['account_key'])
    
len(unique_enrolled_students)
```
* 修改列名 
**用新的列名复制新的一列，然后删除旧列**
```python
for item in dict:
    item["new_naem" ] = item["old_name"]
    del[item["old_name"]]
```

* 过滤掉非部分信息  算是数据清洗的一部分
自己的清洗 Ice and Fire 项目的 charas 信息
**先找到需过滤的信息，生成列表**
```python
def not_main(dict_in):
    not_main_list = []
    for item in dict_in:
        if item['allegiances'] not in main_houses:
            not_main_list.append(item)
    return not_main_list
```
**然后将列表之外的 item 重新组一个 dict**
```python
def remove_not_main(dict_in):
    main_dict = {}
    for item in dict_in:
        if item not in not_main(dict_in): # 使用上一个函数 来获取不是主要 家族的 item 列表
            main_dict.append(item)        # 遍历整个 dict 添加 主要家族成员
   
    return main_dict
```

* 