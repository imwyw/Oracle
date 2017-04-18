* 标量子查询

减少标量子查询，用left join

如下sql中cnt使用的就是标量子查询

```sql
select a.username,(select count(*) from all_objects b where b.owner=a.username) cnt
 from all_users a;

--修改后
select a.username,count(*) 
 from all_users a left join all_objects b on a.username=b.owner
 group by a.username;
```



