psql -U postgres -d postgres
-  SELECT <br>
    pg_terminate_backend(pid) <br>
FROM <br>
    pg_stat_activity <br>
WHERE <br>
    -- don't kill my own connection!<br>
    pid <> pg_backend_pid()<br>
    -- don't kill the connections to other databases<br>
    AND datname = 'NCD'--需要修改数据库据名称<br>
    ;<br>
-  drop database "NCD";<br>
-  CREATE DATABASE "NCD"<br>
  WITH OWNER = dev<br>
       ENCODING = 'UTF8'<br>
       TABLESPACE = pg_default<br>
       LC_COLLATE = 'en_US.UTF-8'<br>
       LC_CTYPE = 'en_US.UTF-8'<br>
       CONNECTION LIMIT = -1;<br>

