建表

create '117', 'cf1','cf2'



调整列族结构

alter '117', { NAME => 'cf1', VERSIONS => 5 }

查看

describe '117'



插入数据(插入数据命令格式：put ‘表名’，‘行值’，‘列族：列名’，‘数据’)

put '117','1','cf1:name','xingdui'

查看

scan '117'



get 'r1', {COLUMN => 'c1'}



get '117', '1', {COLUMN => 'cf1:name'}



get '117', '1', {COLUMN => 'cf1:name', VERSIONS=>3}



扫描部分rowkey数据：

例如 设置rowkey的起和止 ： scan '117', {STARTROW=> '2', STOPROW =>'4'}



查看表中所有数据(通过统计rowkey)

count '117'



通过scan 查看表的 cf1列族的所有数据

scan '117', {COLUMNS=>'cf1'}



通过命令：delete‘表名’,‘行名’,‘列族：列'，时间戳。来删除某个记录

delete '117', '5', 'cf1:name'

Hbase的删除，只是put一个 delete型 的单元格，不带时间戳 相当于put一个当前时间戳 类型为delete的单元格 