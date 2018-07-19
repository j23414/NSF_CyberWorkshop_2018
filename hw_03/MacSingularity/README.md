# Install Singularity on Mac

Singularity requires Ubuntu or Centos operating system and cannot be installed on MacOS. Therefore, we create a ubuntu dockerfile that installs and sets up singularity.

```
$ docker build -t singularityimg .
$ docker run -it singularityimg:latest
```