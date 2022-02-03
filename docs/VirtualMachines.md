# What is a Virtual Machine (VM)
A virtual machine, commonly shortened to just VM, is no different than any other physical computer like a laptop, smart phone, or server. It has a CPU, memory, disks to store your files, and can connect to the internet. While the parts that make up your computer (called hardware) are physical and tangible, VMs are often thought of as virtual computers or software-defined computers within physical servers, existing remotely that can be connect using internet.

# Working of VM
VMs are created with dedicated amounts of CPU, memory, and storage that are "borrowed" from a physical host , mostly remote server—such as a server in a cloud provider's datacenter. A VM is like a computer file, typically called an image, that behaves like an actual computer. It runs as a separate computing environment, often to run a different operating system or when running compute intensive tasks that are n. The virtual machine is partitioned from the rest of the system, meaning that the software inside a VM can't interfere with the host computer's primary operating system.

# Creating VMs on GCP

Creating virtual machines (VM) is one of the primary tasks for performing computational task and analysis in the cloud. While it is very simple to create a VM, it is important to understand the different kinds of VM. The information around google VM’s is listed at https://cloud.google.com/compute. All the VM’s are billed by the hour and the pricing can be checked at https://cloud.google.com/compute/all-pricing. In general, spot instances are always going to be ~70% cheaper than the regular instances.
1.	The first step involves by navigating to https://console.cloud.google.com/ and signing in with your JAX credentials. Remember you should already have access to JAX GCP environment. If not you have to open up a separate ticket for gaining access to JAX GCP environment.
2.	This will direct you to the main dashboard. Make sure you have navigated to the correct project. All the projects that you are currently part of will be listed at the top left side of the GCP pane, marked by red oval in the picture below.
 
3.	Once you confirm that you are in the right project. Find the “Navigation Menu”, denoted by three bars at the top left corner. As indicated by the green circle in the image above.
4.	Scroll to the “COMPUTE” section in the menu. You can scroll to the “VM instance” located within “Compute Engine”. Both the tabs are highlighted with gray in the picture below
 
5.	Once at the VM instance dashboard, we can create a new VM by navigating to “CREATE INSTANCE”. As indicated by the yellow rectangle in the image below.
 
6.	This will open a new page, where we need to provide information relative to the type of instance we want to create. Please, make sure that fill the form completely. The region and zone should be selected according to the network and subnetwork provided in your project. Almost all, unless requested otherwise, of the JAX project network resides in “us-east1” region. Equally important is that we opt for the right VM. Choosing the correct VM is primarily dependent on the kind of workload we intend to carryout. Details on the kind and specification on the VMs can be obtained at https://cloud.google.com/compute/docs/machine-types. In general, the different types of VM’s will be listed when filling the form but it is good to understand the subtle variation beforehand. 
 
7.	There are a lot of options to choose the “Boot Disk” from. We can even use a custom pre-built image or use an existing disk to create the VM. However, it is always easier to create VM from the “Public Images” provide by the google. One of the public images that I use regularly is the Debian operating system Version Linux 10 (buster), selecting Balance persistent disk 10 GB as the Boot Disk type. Also make sure that you have chosen the correct Service account in the “Identity and API access”. This service account should be created when the project was created and allows the VM you create to interact with other google services and API that the VM might interact with.
 
8.	Google SDK command to create the VM:
 

![image](https://user-images.githubusercontent.com/40645366/152385090-9d117350-3fa8-46ff-99f6-6d7e249b289b.png)
