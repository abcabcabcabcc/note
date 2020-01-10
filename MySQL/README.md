
```sql
select * from test where type=4 limit 20000,5;
```
查询到索引叶子节点数据;
根据叶子节点数据上的主键去聚簇索引上查询所需要的全部字段值;
需要查询20005次聚簇索引的数据,最后过滤前20000条,耗费大量随机I/O在查询聚簇索引的数据上

```sql
select * from test a inner join (select * from test where type=4 limit 20000,5) b on a.id=b.id;
```

```sql
select index_name,count(*) from information_schema.INNODB_BUFFER_PAGE where INDEX_NAME in ('val','primary') and TABLE_NAME like '%test%' group by index_name;
```

