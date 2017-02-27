备份数据库：
pg_dump -h 127.0.0.1 -U postgres NCD > /home/ncd
恢复数据库：
psql -h localhost -U postgres -d databasename <  /home/ncd
