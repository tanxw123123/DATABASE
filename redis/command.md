redis客户端安装：ubuntu
```
$ sudo apt install redis-tools
```
登陆redis：
```
$ redis-cli -c -h xxx-redis.xxx.cache.amazonaws.com -p 6379
```
查看redis版本&客户端连接数
```
# redis-cli info | grep 'redis_version'        # 查看版本和客户端连接数
# redis-cli info | grep 'connected_clients'    # 查看客户端连接数
> info       # 进入redis查看也行
```
进入0库：
```
> select 0
```
查看key：
```
> keys *CREATE_GROUP_LOCK*      #查询匹配的key
```
查看key的value：
```
> get key值
```
通配符删除key：
```
$ redis-cli -c -h 主机 -p 6379 -n 0 keys "Api-Gateway:sbod:sbodCache*" | xargs redis-cli -h redis地址 -p 6379 -n 0 del
参数：
-n 指定库编号，上面表示删除0库Api-Gateway:sbod:sbodCache开头的key
```
