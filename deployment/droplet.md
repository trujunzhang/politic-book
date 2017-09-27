## Droplet on the DigitalOcean

### Details (09/01/2017)

```
Droplet address: 128.199.185.13
OS: Ubuntu 16.04.2 LTS (GNU/Linux 4.4.0-96-generic x86_64)
Docker version 17.05.0-ce, build 89658be
```

### Dock PS Information
On digital ocean, list the docker's information.

```
docker ps -a
```

|CONTAINER ID        |IMAGE                     |COMMAND           |           PORTS                      |                    NAMES  |
| -------------------|:------------------------:| ----------------:|-------------------------------------:|--------------------------:|
|06932024185b        | politicl/scrapyd:v6      | "scrapyd"        | 0.0.0.0:6800->6800/tcp               |   politicl-scrapyd        |


### How to bash scrapyd's docker

```
docker exec -it politicl-scrapyd bash
```
