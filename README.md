# Portfolio 2 building a sandbox network
# Aims
A sandboxed network provides an essential learning environment and platform, offering a secure, isolated space to simulate real-world network scenarios without introducing risks to live systems. For this Portfolio, you will create your own private sandboxed virtual network using VirtualBox. The network will consist of multiple virtual machines (VMs) configured within a private IP address range. The aim is to gain an applied understanding of networking concepts, IP subnetting, network interface configuration, and a basic server setup, design, planning and organisation strategies.
# Task
You will create a small network that includes three virtual machine assets that will be networked. They are as follows:

Desktop VM: Used as the management interface for configuring other VMs, on subnet one.

Gateway VM: Acts as the network gateway with three LAN cards. One LAN card with internet access and another two LAN cards denoting two separate subnets.

Application Server VM: Can be any server of choice (e.g., web server, database server), on subnet two.
You can select a prebuilt server from Bitnami if you prefer.
# Devices Used:
1. Ubuntu 24 Desktop: https://ubuntu.com/desktop
2. Ubuntu Server as Gateway Router: https://moodle.roehampton.ac.uk/pluginfile.php/4873277/mod_resource/content/4/Setting%20Up%20a%20Ubuntu%20Gateway%20Router_v02.pdf
3. Bitnami Wordpress: https://bitnami.com/stacks/virtual-machine
# method: 
# Setting ip address in Ubuntu 24 Desktop:
1. Open Network settings and select IPV4 tab and input the ip address provided:

   <img width="600" alt="Ubuntu24_desktop" src="https://github.com/user-attachments/assets/c3ff4d26-7ce6-49f2-bf37-b5ed2ebe9c1e">




   <img width="600" alt="Ubuntu24_desktop_network_setting" src="https://github.com/user-attachments/assets/a44f70a3-04f8-40df-b51a-91f7d9e588b9">

2. Then try pinging the Bitnami and Gateway Router see if its reachable:
   
   <img width="600" alt="Ubuntu24_ping" src="https://github.com/user-attachments/assets/d36af873-e67d-44de-8447-c7593a4312dc">


# Setting ip address in Bitnami Wordpress: 
1. Edit the network interfaces file with the command "sudo nano /etc/network/interfaces", and this file looks like the image below:

   
<img width="650" alt="bitnami_ip_address_setting" src="https://github.com/user-attachments/assets/b81bef2f-748f-4b00-9e39-13e6247fce72">

2. After editing and saving the file, try to ping Ubuntu24 desktop, and Gateway Router:

<img width="600" alt="bitnami_ping" src="https://github.com/user-attachments/assets/22ee2290-9f22-491c-80df-8613095c6a59">

# Setting ip address in Gateway Router: 
1. Edit the network interfaces file with the command "sudo nano /etc/netplan/50-cloud-init.yaml", and this file looks like the image below:

<img width="600" alt="ubuntu_server_router_ip_address_setting" src="https://github.com/user-attachments/assets/2afbfbda-b709-4dd5-941b-ccbc8d967b4c">

2. After editing and saving the file, try to ping Ubuntu24 desktop, and Bitnami:

<img width="600" alt="ubuntu_server_router_ping" src="https://github.com/user-attachments/assets/31bc7b1d-d72a-4112-96cd-30087e09b2fc">

# Conclusion:

After setting all 3 network devices, all three devices are pinging each other ip addresses successfully.
