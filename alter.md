## 修改表结构  ALTER

> 低频操作 包括添加删除字段，修改字段的属性，名字

### change the table name
`alter table stu rename stus;` or  we can do like this:
`rename table stus to stu;`

### **clear** all data of the table but the table is exist.
`truncate stu2;`

### alter column

```
alter table stu2 modify sname varchar(50) not null;
alter table stu2 change sname name varchar(50) not null;
alter table stu2 add sex smallint default null;
alter table stu2 add email varchar(100) default null after sex;
alter table stu2 add qq varchar(20) default null first;
alter table stu2 drop sex;
```



