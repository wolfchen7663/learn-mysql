```
inner join 完全匹配 不存在的就不匹配、
left join (左侧偏心) 左表全部展示 
if 
if(s.class_id, c.cname, '无') 
如果s.class_id 不是 null ,那么就展示 c.cname, 否则就展示无
```

```
自己连接自己
当成两张表对待

SELECT s2.sname FROM stu AS s1 
INNER JOIN stu AS s2 
ON s1.class_id = s2.class_id 
WHERE s1.sname = "houdunren"
AND s2.sname != "houdunren";
```





