# 第一周

## 数据分析有关的python库

**pandas**

 > pandas提供了使我们能够快速便捷地处理结构化数据的大量数据结构和函数。

> pandas具有高性能的数组计算功能以及电子表格和关系型数据（如SQL）灵活的数据处理能力。它提供了复杂精细的索引功能，以便更为便捷地完成重塑、切片和切块、聚合以及选取数据子集等操作。

>  对于金融行业的用户，pandas提供了大量适用于金融数据的高性能时间序列功能和工具。

>　DataFrame是pandas的一个对象，它是一个面向列的二维表结构，且含有行标和列标。

### 一.数据导入和导出
###（一）读取csv文件

 1.本地读取

import pandas as pd

df = pd.read_csv('E:\\tips.csv')  

**根据自己数据文件保存的路径填写(p.s.  python填写路径时，要么使用/，要么使用\\)#输出：**

2.网络读取

import pandas as pd

data_url = "https://raw.githubusercontent.com/mwaskom/seaborn-data/master/tips.csv" 

**填写url读取**

df = pd.read_csv(data_url)

**#输出同上**

###   (二)读取Mysql数据
　　假设数据库安装在本地，用户名为myusername,密码为mypassword,要读取mydb数据库中的数据

import pandas as pd

import MySQLdb

mysql_cn= MySQLdb.connect(host='localhost', port=3306,user='myusername', passwd='mypassword', db='mydb')

df = pd.read_sql('select * from test;', con=mysql_cn)   
 
mysql_cn.close()

上面的代码读取了test表中所有的数据到df中，而df的数据结构为Dataframe。

### (三)读取excel文件

要读取excel文件还需要安装xlrd模块，pip install xlrd即可。

df = pd.read_excel('E:\\tips.xls')


[read more](https://www.cnblogs.com/zzhzhao/p/5269217.html)














