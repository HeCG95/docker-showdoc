# docker-showdoc
**ShowDoc with Docker Compose** 

Using Docker Compose to start a ShowDoc.

## Prerequisite

+ Install [Docker][1] and [Docker Compose][2] in your testing environment

## Start with following steps

+ (0) Download ShowDoc official Docker Image, create home directory:

```
docker pull registry.cn-shenzhen.aliyuncs.com/star7th/showdoc
docker tag registry.cn-shenzhen.aliyuncs.com/star7th/showdoc:latest star7th/showdoc:latest

mkdir -p ./showdoc_data/html
chmod  -R 777 ./showdoc_data
```

+ (1) Start ShowDoc

```
docker-compose up -d
```

The result is 

```
Creating network "showdoc_bridge" with driver "bridge"
Creating showdoc_showdoc_1 ... done
```

+ (2) Check the status of ShowDoc

```
docker-compose ps
```

The result is 

```
      Name                     Command               State                            Ports                         
--------------------------------------------------------------------------------------------------------------------
showdoc_showdoc_1   /entrypoint /bin/sh -c if  ...   Up      443/tcp, 0.0.0.0:4999->80/tcp,:::4999->80/tcp, 9000/tcp
```

Default language is Chinese, you can change it to English:

```
curl http://hostname:4999/install/non_interactive.php?lang=en
```

+ (3) Login ShowDoc with showdoc/123456 : http://hostname:4999


[1]: https://www.docker.com
[2]: https://docs.docker.com/compose/
[3]: https://www.showdoc.com.cn/help/65610/

## License

Apache 2.0 license
