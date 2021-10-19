# k8s-mysql-replication

### At master node
```sql
SHOW MASTER STATUS;
```
example result:
`mysql-bin.000003	156`
### At slave node
```sql
CHANGE MASTER TO MASTER_HOST='192.168.x.x',
MASTER_PORT=30100,
MASTER_USER='root',
MASTER_PASSWORD='changeme,
MASTER_LOG_FILE='mysql-bin.000003',
MASTER_LOG_POS=156;
```
with '192.168.x.x': ip or domain of master node
```sql
start slave;
```
```sql
show slave status;
```
