```
> show variables like '%max_connection%'; 查看最大连接数
> select USER , count(*) from information_schema.processlist group by USER; 查看当前连接中各个用户的连接数
> show status like  'Threads%'; 查看打开的连接数
Threads_connected ：这个数值指的是打开的连接数.
> SHOW GLOBAL VARIABLES LIKE 'wait_timeout'; 查看等待超时时间
> show variables like  '%timeout%';
```
