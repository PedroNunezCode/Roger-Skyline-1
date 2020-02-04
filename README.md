# Roger-Skyline-1
Configuring a secure web server :) 


# Network and Security Part

### You must create a non-root user to connect to the machine and work.
In my case, I created a non-root user while setting up the virtual machine. All I have to do is input the username and password.

### Use sudo, with this user, to be able to perform operation requiring special rights.
To achive this, first install sudo. In order to install sudo, One must be in root user:
```
$su || type root credentials upon vm startup
$ apt-get update -y && apt-get upgrade -y
$ apt-get install sudo vim -y
```

I prefer to use vim but you can use nano which is installed in the vm by default.

Next the `/etc/sudoers` file needs to be updated. The username you created must be given sudo rights.
In root user:
```
nano /etc/sudoers
```
Notice that I used nano. In this case nano will be the easiest because if I wanted to use vim I would have to change the read/write permissions of the file.

By default, on line 20 You will see that the root user has access to all. You will want to add your user to this file.
In my case:

```
# User privilege specification
root  ALL=(ALL:ALL) ALL
nunezcode ALL=(ALL:ALL) ALL
```
![sudoers](images/Sudoers.png)

Save the file and your new user now has sudo rights.

### We don’t want you to use the DHCP service of your machine. You’ve got to configure it to have a static IP and a Netmask in \30.

First Things First, Open your VirtualBoxManager, Click on your current VM. Then click settings->Network-> On Adapter 1 change default NAT to Bridged Adapter.Then Save by clicking OK.

Whilst on your sudo user: type `ip addr` to check your changes. In my case, the name of my Bridged Adapter is `enp0s3` and just a couple lines under that, You will be able to see its current ip address and its port.
![BridgeAdapter](images/BridgeAdapter.png)

