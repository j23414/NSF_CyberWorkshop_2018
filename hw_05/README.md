# iRODS

iRODS is easist to install on Ubuntu or Centos. 


* Install iRODS on [MacOS](https://irods.org/2015/10/native-gui-access-to-irods-on-a-mac-or-linux-desktop/) 
* [Cyverse guide](https://cyverse-data-store-guide.readthedocs-hosted.com)

  * Install icommands
 

## Tutorial

* Login to Jetstream
* Start a webshell

```
$ telnet data.cyverse.org 1247     # connect to cyverse
$ iinit                            # connect to irods
 ERROR: environment_properties::capture: missing environment file. should be at [/home/quietjen/.irods/irods_environment.json]
One or more fields in your iRODS environment file (irods_environment.json) are
missing; please enter them.
Enter the host name (DNS) of the server to connect to: data.cyverse.org
Enter the port number: 1247
Enter your irods user name: quietjen
Enter your irods zone: iplant
Those values will be added to your environment file (for use by
other iCommands) if the login succeeds.

Enter your current iRODS password:
$ ils                       # same as ls, show files
/iplant/home/quietjen:
$ echo "Hello" > one.txt    
$ iput one.txt           # put a file on irods
$ ils
/iplant/home/quietjen:
  one.txt
$ ils -l one.txt         # shows all replicates of the same file
$ ilsresc                # shows all storage
$ irepl one.txt          # make a copy elsewhere
$ ils -l
  quietjen          0 CyVerseRes;ds01Broker;ds01            6 2018-07-20.11:09 & one.txt
  quietjen          1 taccCorralRes;tacc            6 2018-07-20.11:21 & one.txt
$ irepl -R cyverseUKRes one.txt           # repl vs put
$ ils -l
/iplant/home/quietjen:
  quietjen          0 CyVerseRes;ds01Broker;ds01            6 2018-07-20.11:09 & one.txt
  quietjen          1 taccCorralRes;tacc            6 2018-07-20.11:21 & one.txt
  quietjen          2 cyverseUKRes;cyverseUK            6 2018-07-20.11:27 & one.txt
$ iget one.txt two.txt          # pull a copy of the file
$ imeta ls -d one.txt
$ imeta add -d one.txt mod hungry today
```

* HW #5 [Tutorial](https://github.com/irods/irods_training)

```
sudo apt-get -y install irods-rule-engine-plugin-python python-exif
```

