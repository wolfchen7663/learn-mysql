## order by
先筛选条件再排序
```
select * from stu where sex = 2 order by id desc limit 1;

```
**排序是对查询到（筛选后）的结果进行排序 所以在where 的后面**

## field 

```
field ('a', 'a', 'b', 'c') a 在 集合里面 返回1 

select sname, left(sname, 1) as s from stu order by field(s, '陈','李','王') desc;

陈为1 李为2 王为3 
```

## count
```
count(content) 不统计为Null的
count(*) 统计包括为null的
```
## DISTINCT 
去重

## GROUP BY 
**是对查询（筛选）之后的结果进行分组 所以在 where 的后面**

## HAVING
**对分组之后的结果进行筛选**
```
select class_id , count(*) as c from stu group by class_id having c >= 2;
```






