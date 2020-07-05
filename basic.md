### connect mysql
connect mysql use  `mysql -uroot -p`
, `root` is the default username, you should change to your username.
### show all databases

`show databases;`

### create a database
`create database test;`

### delete a database;

`drop database if exists test;`

### use database

`use test;`

### create a table

`create table class (id int auto_increment primary key ,cname varchar(30) not null, description varchar(100) null);`

### delete a table 
`drop table if exists test;`


### add data to table 
`insert into class (cname, description ) values ('Linux','服务器知识'),('Mysql', '数据库知识'),('JS', null);`

or 

`insert into class set cname ='chen', description = 'hansdome';`


### show the table 

`desc class;`


---
**BELOW IS NOT USED USUALLY....**
### copy a table construct and copy the data

`create table school like class;`
`insert into school select * from class;`
if just need one data, we can do like this:
`insert into school (cname) select cname from class;`


or we can do it the fast way just like below:
`create table allCopy select * from class;`

we can also define our own column name:
`create table allCopy (id int auto_increment not null primary key, name not null varchar(30)) select cname as name from class;`

---

### select a table 
`select * from class;`
`select cname, id as ids from class;` here `as` just changes the name of id to ids.

### select where
`select * from class where description  not like '%p%' and id > 1;`


### between and 
`select * from class where age between 20 and 30;`

### in 
`select * from class where age in (20, 30);`

### solve null
null can't compare to any.
`select * from class where class_id is null;`
`select sname, ifnull(class_id, 'not assign') from stu;`

### order by
`select * from class order by class_id asc;` from small to big 
`select * from class order by class_id desc;`from big to small

### get 1
`select * from class order by class_id asc limit 1;`
**limit(para1, para2) ,para1 means index, para2 means count.**

### update

`update stu set class_id where class_id is null;`

### delete 
`delete from stu where age < 30 and class_id is null;`










