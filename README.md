# eureka_cluster
HTTP basic authentication eureka cluster
###step1
用ide打项目（自己的机器配置好gradle）
###stop2
配置本机host
```
127.0.0.1	runghall.local	runghall.localhost
```
###step3
打开Termianl并且进入项目根目录执行 
```shell
gradle build
```
###step4
终端执行
```shell
java -jar java -jar server_cluster/build/libs/server_cluster-1.0-SNAPSHOT.jar --spring.profiles.active=node1    启动eureka集群节点1
java -jar java -jar server_cluster/build/libs/server_cluster-1.0-SNAPSHOT.jar --spring.profiles.active=node2    启动eureka集群节点2
java -jar java -jar server_cluster/build/libs/server_cluster-1.0-SNAPSHOT.jar --spring.profiles.active=node3    启动eureka集群节点3
java -jar client_test/build/libs/client_test-1.0-SNAPSHOT.jar   启动测试客户端
```
###step5
浏览器分别打开huarh:runghall@localhost:1111，huarh:runghall@runghall.local:1112，huarh:runghall@runghall.localhost:1113查看各个分片状态