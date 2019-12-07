## 使用Docker创建服务

```sh
docker run --rm -itd -p 3306:3306 -e MYSQL_ROOT_PASSWORD=mysql mysql
```


```sh
docker exec -it cd51eca84622 sh -c 'exec mysql -uroot -pmysql'
```