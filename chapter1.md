* 减少标量子查询，用left join

```sql
select a.username,(select count(*) from all_objects b where b.owner=a.username) cnt
 from all_users a;
```





