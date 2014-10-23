# docker-adventure-time

Base docker image for [adventure-time](https:/github.com/maxogden/adventure-time) based workshops
that installs node uses [expose-fs](https://github.com/mafintosh/expose-fs) to expose its file system over http

```
docker pull mafintosh/docker-adventure-time
```

Then it your workshop Dockerfile do

```
FROM mafintosh/docker-adventure-time
RUN npm install your-workshop-dependencies
```