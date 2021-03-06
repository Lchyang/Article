## python os 模块的常用操作

### 使用 os.path 模块中的函数来操作路径名。

```
>>> import os
>>> path = '/Users/beazley/Data/data.csv'

>>> # Get the last component of the path 
>>> os.path.basename(path)
'data.csv'

>>> # Get the directory name 
>>> os.path.dirname(path) 
'/Users/beazley/Data'

>>> # Join path components together
>>> os.path.join('tmp', 'data', os.path.basename(path)) 
'tmp/data/data.csv'

>>> # Expand the user's home directory 
>>> path = '~/Data/data.csv'
>>> os.path.expanduser(path) 
'/Users/beazley/Data/data.csv'

>>> # Split the file extension 
>>> os.path.splitext(path) 
('~/Data/data', '.csv')
```

## 获取文件系统中某个目录下的所有文件列表。

```

```
