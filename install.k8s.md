[Back to the index...](https://github.com/Roche-Olivier/help.windows10.nodejs.basics)

### Kubernetes

**Prerequisites**
* 'Docker desktop' needs to be installed.

**Checks**
* Make sure there is no .minikube file in the path : c:\Users\\{username}\.minikube (~/.minikube )
* Kubernetes is not started via your desktop app 'Docker desktop'
* The docker daemon is running.


***


**Set up a new virtual private switch**

In your 'Hyper-V Manager', open the Virtual switch manager, and add the following VPS

* Primary Virtual Switch
* External network

Now you have a new network called `Primary Virtual Switch`

![VPS Setup](https://github.com/Roche-Olivier/Examples/blob/master/Examples/Images/vps_Setup.png "VPS Setup")


***

**Downloading and installing minikube**

The page:<br>
> https://github.com/kubernetes/minikube/releases

The exe<br>
> https://storage.googleapis.com/minikube/releases/v1.1.1/minikube-windows-amd64.exe

Download minikube for windows and save it.

Save the file to a relevant folder for example 'C:\Program Files (x86)\Kubernetes\Minikube'. ( Create your own path , this does not have to be the path its is merely an example )

Rename the file to `minikube.exe`

Now add this directory to your path.

![Class path](https://github.com/Roche-Olivier/Examples/blob/master/Examples/Images/class_path.png "Class path")


To test that the minikube command is working correctly , open a command prompt and type the following command

`> minikube version`

You should get the version number back like this
```
PS C:\WINDOWS\system32> minikube version
minikube version: v1.1.1
```

minikube is now ready to be used, but we first need to set up the VM to integrate to kubernetes


***

**Creating the VM that will run minikube**

We will now create a new VM called minikube , that will run kubernetes v1.10.11 and use the vitual switch "Primary Virtual Switch" as its networking interface.

Type in the following command on an administrator privileged power-shell window

`minikube start --vm-driver=hyperv --kubernetes-version="v1.10.11" --hyperv-virtual-switch="Primary Virtual Switch" --memory 2048`


> Please note do not decrease the `memory 2048`, it will cause an out of memory error.


The output should be something like this :

```
PS C:\WINDOWS\system32> minikube start --vm-driver=hyperv --kubernetes-version="v1.10.11" --hyperv-virtual-switch="Prima
ry Virtual Switch" --memory 2048
* minikube v1.1.1 on windows (amd64)
* Creating hyperv VM (CPUs=2, Memory=2048MB, Disk=20000MB) ...
* Configuring environment for Kubernetes v1.10.11 on Docker 18.09.6
* Pulling images ...
* Unable to pull images, which may be OK: pull command is not supported by kubeadm v1.10.11
* Launching Kubernetes ...
* Verifying: apiserver proxy etcd scheduler controller dns
* Done! kubectl is now configured to use "minikube"
```

You can now open your dashboard by typing the following command:

`> minikube dashboard`
 
This will open a web page with your Kubernetes cluster

[Back to the index...](https://github.com/Roche-Olivier/help.windows10.nodejs.basics)