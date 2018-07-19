# Cavatica

* Create containers for [Cavatica](https://github.com/incertae-sedis/cavatica.git)

Requires

* bash
* R (issues with installing packages, looking for an image)
* perl
* (commandline version of Mango, working on it...)

Implementation

* provide a docker solution
* provide a singularity solution
* upload to Hubs (both)

Dockerfile

```
$ docker build -t cavatica .      # Build docker image
$ docker run -it cavatica:latest  # Run interactively
```

Singularity file

```
$ singularity build cavatica.simg cavatica.def  # build image
$ singularity shell cavatica.simg               # run interactively
```


