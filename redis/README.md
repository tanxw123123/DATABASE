登陆redis：
```
$ redis-cli -c -h xxx-redis.xxx.cache.amazonaws.com -p 6379
```
进入0库：
```
> select 0
```
查看key：
```
> keys *CREATE_GROUP_LOCK*      #查询匹配的key
```
通配符删除key：
```
$ redis-cli -c -h 主机 -p 6379 -n 0 keys "Api-Gateway:sbod:sbodCache*" | xargs redis-cli -h redis地址 -p 6379 -n 0 del
参数：
-n 指定库编号，上面表示删除0库Api-Gateway:sbod:sbodCache开头的key
```