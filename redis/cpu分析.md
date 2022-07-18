cpu过高的原因：
```
1、连接数过多，通过redis-cli info | grep connected_clients查看
2、慢查询，因为redis是单线程，如果有慢查询的话，会阻塞住之后的操作，通过redis日志查 
3、value值过大？比如value几十兆，当然这种情况比较少，其实也可以看做是慢查询的一种
4、aof重写/rdb fork发生？瞬间会堵一下Redis服务器
```
解决方案：
```
1. 关闭僵尸连接,采用redi-cli登录, 采用client kill ip:port(redis远程连接的ip和端口)。 需要采用脚本批量删除多个连接
2. 修改redis timeout参数, 采用redis-cli登录，采用config set timeout xx 设置redis的keepalive时间
3. 修改redis进程的文件数限制, echo -n "Max open files  3000:3000" >  /proc/PID/limits
4. 修改系统参数的最大文件数限制, /etc/security/limits.conf 
```
