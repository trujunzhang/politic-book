## Scrapyd Server(docker)(@deploy):

### Installation

using [https://github.com/Fuxingloh/docker-scrapyd/blob/master/1.2.0/Dockerfile] docker to deploy scrapyd.

#### Scrapyd using Docker's container

```
cd docker/scrapyd && docker build -t politicl/scrapyd:v6 .

docker run \
       --restart=always \
       -t -d -i -p 6800:6800 \
       -v /var/docker_data/scrapyd:/var/lib/scrapyd \
       --name politicl-scrapyd  politicl/scrapyd:v6

$ docker exec -it politicl-scrapyd bash

```

#### Schedular the scripts per 30 minutes

Firstly, ssh the droplet as root, then run the following commander.

```
crontab -e
```

Finally, paste the following and save it.

```
*/30 * * * * curl http://localhost:6800/schedule.json -d project=cwpoliticl -d spider=politicl_watch
*/30 * * * * curl http://localhost:6800/schedule.json -d project=cwpoliticl -d spider=politicl
```


