# Snort Installation and Configuration
### This projects guides on how to install and configure *Snort* inside a virtual machine or your server.
### What is Snort? 
Snort is an open-source intrusion detection system (IDS) that uses a series of rules that help define malicious network activity and uses those rules to find packets that match against them and generates alerts for users.
## Installing Snort
#### Inside your virtual machine (like *Ubuntu* server) run the following command

<img width="568" height="130" alt="image" src="https://github.com/user-attachments/assets/bdaa38d5-6a0e-4b90-9814-965a267acba5" />

#### Configuring the network address you want to protect

<img width="691" height="29" alt="image" src="https://github.com/user-attachments/assets/f5006de8-422d-42c1-9639-4402050efc94" />
<img width="692" height="312" alt="image" src="https://github.com/user-attachments/assets/faa80a6d-6639-419f-b3a3-1cd5d53ae465" />

#### Starting Snort IDS on enp0s3

<img width="755" height="137" alt="image" src="https://github.com/user-attachments/assets/a9c3a039-7ea9-49d6-841c-04d2f95e835b" />

#### Pinging from the other device and triggering and alert

<img width="1200" height="520" alt="image" src="https://github.com/user-attachments/assets/348a20d0-4f97-4df2-ab14-f2857ad8bc7b" />

<img width="819" height="428" alt="image" src="https://github.com/user-attachments/assets/4b71b15f-b5ec-4ce7-b89b-70b6019a541b" />

<img width="816" height="425" alt="image" src="https://github.com/user-attachments/assets/b5f6a9f9-f953-480f-8628-626fb0c1442a" />

#### Adding a rule for this alert
To add a custom rule to the snort, we can add it manually to the “local.rules” file in the “/etc/snort/rules” path. We can construct and add our local rules to this file using any file editor.

<img width="739" height="83" alt="image" src="https://github.com/user-attachments/assets/35c7aa78-f852-4c04-8b71-c840d8ed9fd5" />
<img width="728" height="141" alt="image" src="https://github.com/user-attachments/assets/58d46efd-9614-4f76-a962-d3b396e4d83f" />
<img width="733" height="76" alt="image" src="https://github.com/user-attachments/assets/98c5a86f-7ce0-43e4-add6-3ed4cc161dad" />

For example, if we wanted to add a rule that will fire when you browse to craigslist.org from the machine Snort is running on; it should look for any outbound TCP request to craigslist.org and alert on it.

<img width="729" height="137" alt="image" src="https://github.com/user-attachments/assets/42689a2a-b1f9-4ba4-90be-efc3a350edab" />
<img width="731" height="110" alt="image" src="https://github.com/user-attachments/assets/d5b59950-532e-41d3-9691-1c7da77d6fd0" />

#### You can add or remove rules from the "local.rules" file. 
#### That is a how you can install and configure snort in your virtual machine or your server.
<--- Practice Makes Permanant --->
