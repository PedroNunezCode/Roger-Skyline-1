# Roger-Skyline-1
Configuring a secure web server :) 


# Network and Security Part

## You must create a non-root user to connect to the machine and work.
In my case, I created a non-root user while setting up the virtual machine. All I have to do is input the username and password.

## Use sudo, with this user, to be able to perform operation requiring special rights.
To achive this, first install sudo. In order to install sudo, One must be in root user:
```
$su || type root credentials upon vm startup
$ apt-get update -y && apt-get upgrade -y
$ apt-get install sudo vim -y
```

I prefer to use vim but you can use nano which is installed in the vm by default.
