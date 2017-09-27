## Scrapyd Server(docker version)

#### Requirements

Using Fuxingloh's Docker File to deploy scrapyd.
 
```
https://github.com/Fuxingloh/docker-scrapyd/blob/master/1.2.0/Dockerfile
```

#### Install scrapyd as Docker's container

Run the following commander to create a docker's container.

```
cd docker/scrapyd && docker build -t politicl/scrapyd:v6 .

docker run \
       --restart=always \
       -t -d -i -p 6800:6800 \
       -v /var/docker_data/scrapyd:/var/lib/scrapyd \
       --name politicl-scrapyd  politicl/scrapyd:v6
```

To bash the created scrapyd docker, run the following commander.

```
$ docker exec -it politicl-scrapyd bash
```

#### Remote to access the scrapyd server

Open your favorite browser, type the following url to access the scrapyd server.
```
http://128.199.185.13:6800/
```

## Using it Now
After installed the docker's container. It is just a python server.
Next step is that how to deploy our 'politicl-crawler-scraper' and run it as scheduled tasks.

#### How to schedule the scripts per 30 minutes

Firstly, ssh the droplet as root, then run the following commander.

```
crontab -e
```

Finally, paste the following and save it.

```
*/30 * * * * curl http://localhost:6800/schedule.json -d project=cwpoliticl -d spider=politicl_watch
*/30 * * * * curl http://localhost:6800/schedule.json -d project=cwpoliticl -d spider=politicl
```

### Python Configure File (.newspoliticl)

```
{
"MAX_COUNT_PER_TIME":4,
"MG_HOST":"mongodb://admin:Politicl%40123@ds121882-a0.mlab.com:21882,ds121882-a1.mlab.com:21882/politicldatabase?replicaSet=rs-ds121882",
"MG_COLLECTION":"politicldatabase",
"TOPICS_FILTER_KEYS":"Opinion,India,Politics,News,Society,Porn,Fuck,Sex",
"CLOUDINARY":{
        "CLOUDINARY_IMAGE_NAME":"politicl-meteor",
        "CLOUDINARY_IMAGE_PORT":"80",
        "cloudinaryCloudName": "politicl",
        "cloudinaryAPIKey": "898859385545283",
        "cloudinaryAPISecret": "0D4cT8wmYGEzi6Lz4b0Q2C_r7KM",
        "cloudinaryFormats": [
            {
              "name": "small",
              "width": 100,
              "height": 100
            }
          ]
    }
}

```


