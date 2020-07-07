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

### 时间函数
```
获得当前时间明细
select year (now()), month(now()), day(now()), hour (now()), minute (now()), second (now());

当前具体日期加时间， 当前日期，当前时间
select now(), current_date(), current_time();  

当前是星期几 
1 - 7 1 是星期日 7是星期六
select  dayofweek(now());  

当前的工作日
0-6 0 星期一 6 星期日
select weekday(now());

set @time = time(now());
select @time;
把时间转换为秒数
select time_to_sec(@time);

元年到现在的天数
select to_days(now());

根据天数判断年
select from_days(to_days(now()) ); 

相隔的天数
select  datediff(now(), birthday) from stu;

相隔的时间，只计算时间，不计算天数
select timediff (time(now()),time(birthday)) from stu;

取间隔的通用函数
TIMESTAMPDIFF(unit,datetime_expr1,datetime_expr2);
The unit should be one of the following : SECOND, MINUTE, HOUR, DAY, WEEK, MONTH, QUARTER, or YEAR.
```

```
增加时间
addtime(now(), '08:00:00')
date_add(now(), interval (+-)7 day) 加7或者减7都可以
DATE_ADD(date, INTERVAL expr unit)
减少时间
DATE_SUB(date, INTERVAL expr unit)

```

```
月初与月末
当前月的月初
select date_sub(now(), interval dayofmonth(now())-1 day);
select last_day(now()); 当前日期所在月份的最后一天

上个月的最后一天
select last_day(date_sub(now(), interval 1 month));
下个月的第一天
select date_add(last_day(now()), interval 1 day);
```

```
周的控制
计算一周内星期二是哪天
date_add(now(), interval 3 - dayofweek(now()) day);

date_add(now(), interval 1 - weekday(now()) day);
```


```
按月考勤打卡

```






