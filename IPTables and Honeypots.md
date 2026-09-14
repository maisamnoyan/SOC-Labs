# Installing IPTables and Cowrie Honeypot
### This poject will walkthrough the installation and configuration of *IPTables and the Cowrie Honeypot*
*Make sure you have a running Virtual Environment*
## Installing and Configuring IPTables
- Installing IPTables
<img width="975" height="241" alt="image" src="https://github.com/user-attachments/assets/f0d305f4-1a27-4f77-b9d7-08b88db5f5ba" />

- Checking current Iptables status
<img width="975" height="314" alt="image" src="https://github.com/user-attachments/assets/b7b7b357-9bd1-494d-b629-97b8219498df" />

- Defining chain rules
<img width="975" height="93" alt="image" src="https://github.com/user-attachments/assets/54d61b32-7886-4bb0-8d30-5ade15935c34" />

- Enabling Traffic on localhost
<img width="975" height="61" alt="image" src="https://github.com/user-attachments/assets/5acff55b-992e-4e2c-9a20-55a070e1f8b1" />

- Enabling connections on HTTP, SSH, and SSL ports
<img width="975" height="134" alt="image" src="https://github.com/user-attachments/assets/5d3a5d05-efb2-4c70-abe1-ba365f86c95c" />

- Filtering packets based on source
<img width="975" height="129" alt="image" src="https://github.com/user-attachments/assets/e3fdc100-66f9-4fc5-8c84-39a8937bce0f" />

- Dropping all other traffic
<img width="975" height="573" alt="image" src="https://github.com/user-attachments/assets/960c786b-2b16-454b-bcf2-ca8517e5eda4" />

- Deleting rules
<img width="975" height="59" alt="image" src="https://github.com/user-attachments/assets/b44b5b7a-010b-41fd-bdd3-aaa2103a263b" />

- Persisting changes
<img width="975" height="227" alt="image" src="https://github.com/user-attachments/assets/3022aa14-6227-4f82-8dde-708716778225" />

- iptables-save and iptables-restore
<img width="975" height="56" alt="image" src="https://github.com/user-attachments/assets/f5abc3e9-4b06-4d89-8710-ac610b105cc3" />

- Preserving iptables rules across reboots
<img width="975" height="1002" alt="image" src="https://github.com/user-attachments/assets/9ba9d063-854a-42c8-96af-cd42c03a4fe8" />

### Some useful sample rules for the IPTables - try on your environment
- Accepts all incoming traffic on the loopback interface `iptables -A INPUT -i lo -p all -j ACCEPT`
- Drops all traffic coming from localhost on the eth0 interface `iptables -A INPUT -p all -s localhost -i eth0 -j DROP`
- Accepts all TCP traffic to < your ip address > via eth0 `iptables -A INPUT -s 0/0 -i eth0 -d < IP address > -p TCP -j ACCEPT`
- Accepts TCP traffic from any source on eth0 to < ip address > on eht1, with source port 1024-65535 and destination port 80. `iptables -A FORWARD -s 0/0 -i eth0 -d < IP address > -o eth1 -p TCP \ --sport 1024:65535 --dport 80 -j ACCEPT`
- Blocking a specific subnet ex: 192.168.2.x `sudo iptables -A INPUT -s 192.168.2.0/24 -j DROP`
- Restricting SSH to allow only specific IP addresses `sudo iptables -A INPUT -p tcp –dport 22 -s <specific IP address> -j ACCEPT`
- Blocking any HTTP browsing from the virtual machine ` sudo iptables -A OUTPUT -p tcp --dport 80 -j DROP`
- Block any HTTPS browsing from the virtual machine ` sudo iptables -A OUTPUT -p tcp --dport 443 -j  DROP`
- Rate-limiting ICMP (Ping) traffic to 5 packets per second ` sudo iptables -A INPUT -p icmp --icmp-type echo-request -m limit --limit 5/sec -j ACCEPT `
- Allow only incoming SSH connections ` sudo iptables -A INPUT -p tcp --dport 22 -j ACCEPT `
- Block all incoming TCP traffic. ` sudo iptables -A INPUT -p tcp -j DROP `
- Block all incoming UDP traffic.` sudo iptables -A INPUT -p udp -j `

## Installing and Configuring the Honeypot
- Installing dependencies
<img width="982" height="134" alt="image" src="https://github.com/user-attachments/assets/5af00b8f-57a8-42ba-b104-ddf5b13d47a2" />

- installing SSH - incase you do not have it on your environment
<img width="974" height="648" alt="image" src="https://github.com/user-attachments/assets/cb729e7f-ef38-41f5-94fa-80e249a52697" />

- Editing SSH configuration file
<img width="974" height="747" alt="image" src="https://github.com/user-attachments/assets/aadbf11d-0b2b-4626-a56d-cbc71b790f0a" />

- Restarting SSH
<img width="974" height="64" alt="image" src="https://github.com/user-attachments/assets/ecf1dfed-e2d9-419a-a6c1-7fc973ceee84" />

### Installing Cowrie
- creating a new user called cowrie
<img width="974" height="494" alt="image" src="https://github.com/user-attachments/assets/e5ba17df-5004-40ec-b839-51f7c0b41da5" />

- Logging in as cowrie user
<img width="975" height="86" alt="image" src="https://github.com/user-attachments/assets/5065cbd5-49c2-4da9-8e3d-766b5788dc75" />

- Downloading the cowrie - [Download Link](https://github.com/micheloosterhof/cowrie)
<img width="974" height="352" alt="image" src="https://github.com/user-attachments/assets/6c94c211-a2dc-4934-a430-a96467a00812" />

- Creating a virtual environment
<img width="973" height="246" alt="image" src="https://github.com/user-attachments/assets/7e9c776d-58ea-41ae-be25-406e86fdaa31" />

- Activating the cowrie honeypot
<img width="975" height="425" alt="image" src="https://github.com/user-attachments/assets/beea1760-d8f9-453f-b7cd-57aa1c588d3b" />

- Installing or upgrading pip `pip install --upgrade pip`
- Installing the requirements for cowrie honeypot
<img width="975" height="675" alt="image" src="https://github.com/user-attachments/assets/eb02897e-144f-4217-85e8-b6f23f3260ae" />

- Making a copy of cowrie.cfg
<img width="974" height="148" alt="image" src="https://github.com/user-attachments/assets/6f76ec22-3f0c-44a4-8d64-ad8c2e2619d7" />
<img width="975" height="577" alt="image" src="https://github.com/user-attachments/assets/bb72cc32-30d0-4998-9786-615af8938780" />
<img width="973" height="88" alt="image" src="https://github.com/user-attachments/assets/0b9feebc-6809-413f-a325-bb16a9cc9f43" />

- Adding a rule to silently redirect any incoming traffic to Port 22 to Port 2222
<img width="974" height="139" alt="image" src="https://github.com/user-attachments/assets/fb7bcbb8-1c61-4849-a60e-6782baa84b59" />

- Starting Cowrie honeypot
<img width="975" height="542" alt="image" src="https://github.com/user-attachments/assets/61b1ac52-e650-40aa-ad55-afe45d8eb6fd" />

- Monitoring & Attacking the Honeypot
<img width="975" height="313" alt="image" src="https://github.com/user-attachments/assets/4c1d8b3a-211b-4c65-a66d-7ec1650db927" />
<img width="975" height="450" alt="image" src="https://github.com/user-attachments/assets/3028b9d6-9806-4f74-a2c5-b4ce94b812b5" />

#### You can play with rules and explore further on using this honeypot
<-- Practice Makes Permanent -->


