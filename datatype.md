字符集
- utf8

### 字符串
```
replace(str, find_string,replace_with);
replace(被替换的字符串，字符串的具体被替换的部分，替换的字符串);
replace('chenwei', 'w', 'j');
=> 'chenjei'
```

```
substring(str, from_pos, count); from_pos 从1开始计算
substring(被截取的字符串，开始的位置（默认为1），数量);
substring('chenwei', 2, 3) 
=>'hen'
```

```
left('chenwei', 2) => ch
right('chenwei',2) => ei;
mid('chenwei', 2, 2) =>'he'
```

```
concat('chen', 'wei') => 'chenwei'
```


```
like '%q%' => 包括q就被选中,% 表示一个或多个
like '_q%' => 第二个是q就被选中，_表示一个
```

```
regexp '^.h' => 第二个是h被选中.
```

---

## 数值类型

```
tinyint 
smallint
mediumint
int 
bigint
选取够用就行.
```

`unsigned` 非负数

```
int(num) zerofill
num 表示只显示 num 位数，zerofill 表示位数不够的话，用 0 来填充
```

```
float(总位数，小数位数) 适合总位数7位以下
double(总位数，小数位数)
decimal(总位数，小数位数) 货币数据需要选择这个
```

```
enum 性别就选用这个
enum('男','女') 男为1 女为2
对应应用于单选框
```

```
set('tag1','tag2','tag3)
对应于多选框 标签
for example=>
insert into article (tittle, click, flag) values ('chen', '1000', 'tag1, tag2, tag3');
查找:
select * from article where find_in_set('tag1',flag);
在flag 字段里查找set 类型是 tag1的记录

select * from article where flag like '%tag1%';
在flag 字段里查找set 类型是 tag1的记录
```

```
二进制操作set类型
tag1 0001  1 
tag2 0010  2 
tag3 0100  4 
tag4 1000  8

select * from article where flag & 1; 找到 tag1
select * from article where flag & 10; 找到 tag2 tag4 
```







