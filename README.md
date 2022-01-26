# multipass Mac deployment script with cloud-init

Please note the script does not check or validate the input, just use the help and follow the instructions

This script also assume that you have created a a virtual network on VirtualBox
If you didn't, please follow this steps:

Open terminal and run

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
