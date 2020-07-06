### 格式化输出日期 date_format
```
select sname, date_format(birthday, "%Y年%m月%d日") as birthday from stu;
```

### 格式化时间 time_format
```
select sname, time_format(birthday, "%h:%i:%s") as time from stu;
```
### timestamp 自动更新
```
alter table stu add updated_at timestamp default current_timestamp on update current_timestamp ;
```







