# Homework 3

* Working with containers
* Docker image file
* Singularity file

## Local Install Docker

* requires root access
* Download [Docker.dmg](https://docs.docker.com/docker-for-mac/install/)

## Jetstream setup

* Set up a [DockerHub](https://hub.docker.com/) account
* Navigate to [use.jetstream-cloud.org](https://use.jetstream-cloud.org)
* Login as XSEDE
* Create Project (University of Indiana)
* Open a webshell


```
ez                            # pkg manager
ezd                           # updates docker
docker run hello-world        # check if docker works
sudo docker run hello-world   # docker requires sudo permissions
sudo docker ps                # shows running containers
sudo docker ps -a             # shows past run containers
```

Highly recommended to build off of `alpine` or `busybox` since they have a unix operating system with a small memory cost.

```
sudo -
docker run alpine:3.5                       # pull image of basic operating system
docker run -i -t alpine:3.5                 # interactive run
# apk update                                # for alpine, always update.
# apk add git                               # use apt-get on ubuntu
# exit                                      # exit the docker container
docker run alpine:3.5 echo "hello world"    # Run a command from host
docker run alpine:3.5 script.sh             # Run a script (not quite, did not run)
docker search beast                         # search for an image containing "beast"
docker images                               # lists all images on this machine
```

Create a docker image

```
mkdir test
cd test
touch Dockerfile                            # edit this
docker build -t nameofimage .               # builds image
docker run nameofimage:latest               # run newly created docker image
```

Publicize docker image (send to dockerhub)

```
git clone yournewdockergithub.git
cd yournewdockergithub
mv ~/test/Dockerfile .
git add Dockerfile
git commit -m "newdockerfile" Dockerfile
git push origin master
```

See next section to push to dockerhub.

## DockerHub and GitHub

* Upper right corner, `profile`/`settings`/`Linked accounts and services`
* `Link GitHub`
* Top right corner, `Create`/`Creaet Automated Build` 
