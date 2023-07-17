# How to disable fast mirror yum plugin in CentOS Linux server

See all Sun CentOS Linux related FAQsThis might sound little crazy, but I want to disable yum plugin called the fast mirror. 
It always selects mirror hosted in my country which is very slow. 
As a result of all my yum command download file at 4-8Kb/s only. 
I am also behind a proxy server. How do I disable the fastest mirror plugin on CentOS Linux 6 or 7 server?
The fastest mirror plugin is intended for use in repository configurations where you have more than one mirror in a repo configuration. 
It makes yum to download packages from fastest and nearest mirror. If you are using the default CentOS configuration, and if you are not behind a proxy server, the fastest mirror is very much recommended option for everyone.

## Disable yum command fastestmirror plugin on CentOS/Fedora 
## You need to edit the file named /etc/yum/pluginconf.d/fastestmirror.conf , run:
```
$ sudo vi /etc/yum/pluginconf.d/fastestmirror.conf
```

### Find line that read as follows:
```
enabled=1
```

### And set it as follows (set enabled to 0):
```enabled=0```

### Save and close the file. Now run the following yum command:
```
$ sudo yum clean all
```

### Sample outputs:
```
Cleaning repos: base epel extras updates
Cleaning up everything
```

### Run yum update again:
```
$ sudo yum update
```

### try installing something
```
$ sudo yum install pkg
```
```
$ sudo yum install htop
```
