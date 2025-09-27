# Palo-Alto-1
Configuring a palo alto firewall on basic network topology

1) This is a basic network with two Windows 7 PCs, a Palo Alto VM firewall and a connection to the Internet. I haven't added too many nodes because of memory restritctions. PC Tester has been assigned the IP address- 10.1.1.20/24, PC PA-mgmt has been assigned 192.168.0.10/24. The mgmt interface has been configured with an interface IP address of 192.168.0.1/24 and eth 1/1 has been assigned 10.1.1.10/24.
<img width="928" height="441" alt="image" src="https://github.com/user-attachments/assets/104a5044-2938-41c3-956e-57d5513eb7cf" />



2) I have configured all required interfaces as Layer 3 interfaces. The inside interface, ethernet 1/1 has been assigned the security zone- Inside. The interface facing the internet- ethernet 1/2 has been assigned the outside security zone. The virtual router 'Contractors' is from a previous project so excuse it. Additionally, eth 1/2 is configured as a DHCP client so that it gets an IP from the internet. 
<img width="1278" height="748" alt="image" src="https://github.com/user-attachments/assets/3631c338-a84e-46e8-975b-54460a03402d" />



3) Configured a security policy to allow traffic from the inside zone to the outside zone. Since this policy is meant to allow all traffic from the inside zone to the outside zone, the application, URL and services options have not been tweaked. The action is configured to allow all traffic.
<img width="1275" height="747" alt="image" src="https://github.com/user-attachments/assets/911d908f-56cd-40e4-8e9f-eb197da97a1f" />



4) Configured a NAT policy for users in the inside zone who want to access the internet. The NAT is configured as a PAT/overload NAT so that traffic from the inside zone when exiting the outside interface, takes the IP of the outside interface a unique port number. 
<img width="1276" height="755" alt="image" src="https://github.com/user-attachments/assets/b97fa6ff-9409-4db8-8512-420f19df31aa" />



5) The changes are committed to the firewall's memory and are tested using the Tester PC. A request to google is made which is then subsequently logged by the firewall and displayed in the session browser option in the monitor tab of the firewall. 
<img width="1276" height="752" alt="image" src="https://github.com/user-attachments/assets/77eb01c2-744e-4fe9-992f-b08438a93216" />
