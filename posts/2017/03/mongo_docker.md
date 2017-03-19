## Abstract  
running mongodb on local machine by using mongo's docker image

## Steps
1.pull mongo image from dockerhub
```bash
$ docker pull mongo
Using default tag: latest
latest: Pulling from library/mongo
693502eb7dfb: Pull complete
5a29f630b22e: Pull complete
328ac2c79d69: Pull complete
d628f74e0e97: Pull complete
50753de132e0: Pull complete
14fee098631b: Pull complete
7a4c3bdc1525: Pull complete
afe0970b86ae: Pull complete
b3fbca93d344: Pull complete
Digest: sha256:3d4537f996bc28a6c6b694e22f46316c0629703420de60e8f46285ce1fe69260
Status: Downloaded newer image for mongo:latest
```

2. run image with docker run command
```bash
$ docker run -d  --name mongo_1 -p 27017:27017 mongo
```
### explanations of options 
* -d               : to run mongo as a daemon. if we omit this option, after running the container, we'll be prompted to the container's logs.
* --name mongo_1   : to give an user friendly name to the container. 
* -p 27017:27017   : by default mongo's docker image is configured to accept connections through port 27017. with this option, we are redirecting connections coming to our local hachine's port 27017 to the container we run. 

3. by using robomongo, we are able to connect mongodb now. to connect to the mongodb, type 127.0.0.1:27017 in the address field.  

4. (optional) to tail logs on the container:
```bash
$ docker logs --follow mongo_1
```
    