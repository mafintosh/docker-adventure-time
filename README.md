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

If you want to add a welcome text add it do `/welcome.txt` in the container.
`{{host}}` will be replaced with `$HOST` which is the http address to this container
and `{{container-id}}` will be replaced with the id of the container

An example `welcome.txt` could be

```
Welcome to my workshop
Listen on port 80 and you can access that server using {{host}}
```

And to add use the `ADD` stanza in your Dockerfile

```
FROM mafintosh/docker-adventure-time
RUN npm install your-workshop-dependencies
ADD welcome.txt /
```
