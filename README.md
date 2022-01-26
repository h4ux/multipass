# Multipass Mac deployment script with cloud-init

Please note the script does not check or validate the input, just use the help and follow the instructions

This script also assume the following: 

- You have VirtualBox installed
- You have Multipass Installed
- You have set multipass local.driver to VirtualBox
- You have created a virtual network on VirtualBox

If you didn't do any of the following, please follow this steps:

> To install VirtualBox please visit: [VirtualBox Download](https://www.oracle.com/technetwork/server-storage/virtualbox/downloads/index.html)
> 
> To install Multipass You can use **brew install --cask multipass** but i suggest to use Multipass PKG as it installs also a nice tool that seats in the Menu bar.
Grab it here: [Multipass Mac download](https://multipass.run/download/macos)

> To set multipass driver to VirtualBox run
>```
>sudo multipass set local.driver=virtualbox
>```

### To create a virtual network open terminal and run

```
Sudo VirtualBox
```

Click on:

    File --> 
    
            Host Network Manager --> 
        
                                    Create
            
Then
```
Click on DHCP Server Tab of the new network and check the Enable Server checkbox
```

It should look something like this:

![image](https://user-images.githubusercontent.com/77572830/151146703-b06c034e-db96-4d6d-9869-68422e9659a0.png)

## Launch a multipass VM with cloud-init

```
Syntax: sudo sh launch-vm [-n|f|m|d|c|h]
options:
-n     Name of the instance
-f     cloud init file path
-m     memory for instance, default to 4GB if empty
-d     drive size for instance, default to 20GB if empty
-c     number of vCPU, default to 2 if empty
-v     name of the virtual network, default to vboxnet0
-h     display this help!!!
```

```
Please run using sudo (sudo sh launch-vm)
For help run sh launch-vm -h
```

Example:
```
sudo sh launch-vm -n k8-kind -f cloud-init-k8-kind.yaml
```
