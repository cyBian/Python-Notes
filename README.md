# :snail: Python Notes 

## 1. 创建目录

python 对文件操作主要会用到os模块：

主要涉及到三个函数：

+ os. path.exists(path)  #  判断一个目录是否存在
+ os.makedirs(path)      #  创建多级目录
+ os.mkdir(path)             #  创建单级目录
  ``` python
  #!/user/local/bin/python2.7
  # -*- coding:utf-8 -*-
  # 引入模块
  import os
  def mkdir(path):
  # 去除首位空格
  path=path.strip()
  # 去除尾部 \ 符号
  path=path.rstrip("\\")
  # 判断路径是否存在
  isExists=os.path.exists(path)
  # 判断结果
  if not isExists:
  # 如果不存在则创建目录,创建目录操作函数
  '''
  os.mkdir(path)与os.makedirs(path)的区别是,当父目录不存在的时候os.mkdir(path)不会创建，os.makedirs(path)则会创建父目录
  '''
  #此处路径最好使用utf-8解码，否则在磁盘中可能会出现乱码的情况
  os.makedirs(path.decode('utf-8')) 
  print path+' 创建成功'
  return True
  else:
  # 如果目录存在则不创建，并提示目录已存在
  print path+' 目录已存在'
  return False
  # 定义要创建的目录
  path=r"d:\\web天下\\"
  # 调用函数
  mkdir(path)
  ```
  > 来源：

## 2. 获取当前工作路径

    + sys.argv[0]
  ``` python
  import sys
  print sys.argv[0] # 获取的是当前执行脚本的位置
  ```
  运行结果：

    > F:/SEG/myResearch/myProject_2/test.py

+ os模块
  ``` python 
  import os
  print(os.getcwd())                # 获得当前工作目录
  print(os.path.abspath('.'))       # 获得当前工作目录
  print(os.path.abspath('..'))      # 获得当前工作目录的父目录
  print(os.path.abspath(os.curdir)) # 获得当前工作目录
  ```
  运行结果：
  > F:/SEG/myResearch/myProject_2
  > F:/SEG/myResearch/myProject_2
  > F:/SEG/myResearch
  > F:/SEG/myResearch/myProject_2

**原文参见：**[python-获取当前路径](https://blog.csdn.net/qq_15188017/article/details/53991216)

## 3. 画图
### 3.1 为字体添加上下标
``` python
plt.xlabel('a/${m_2}$', fontdict={'weight':'normal', 'size':15})
plt.xlabel('a/$\mathregular{m_2}$', fontdict={'weight':'normal', 'size':15})  # 去掉斜体格式
set_label( '($\mathregular{m^2}\mathregular{m^{-2}}$)', fontsize=11)
```
