# task-4-firewall-configuration

🔐 Firewall Configuration in Kali Linux (UFW) 


📘 Steps Involved


- 🟢 Step 1: Open Firewall Configuration Tool
Install and enable UFW, the front-end for iptables.
sudo apt update
sudo apt install ufw -y
sudo ufw enable


- 🔵 Step 2: List Current Firewall Rules
Check the baseline configuration before making changes.
sudo ufw status verbose

- 🔴 Step 3: Block Inbound Traffic on Port 23 (Telnet)
Telnet is insecure and often exploited, so block it.
sudo ufw deny 23/tcp

- 🟠 Step 4: Test the Rule
Attempting to connect should fail.
- Locally:
telnet localhost 23
- Remotely:
telnet <your_kali_ip> 23

- 🟣 Step 5: Allow SSH (Port 22)
SSH is essential for secure remote administration.
sudo ufw allow 22/tcp

- 🟡 Step 6: Remove the Test Block Rule
Restore the firewall to its original state.
sudo ufw delete deny 23/tcp

- ⚪ Step 7: Document Commands Used
Keep a record for reproducibility and audits.


- 🟤 Step 8: Summarize How Firewalls Filter Traffic
Firewalls act as gatekeepers, inspecting packets and applying rules to decide whether to allow or block them. UFW translates rules into iptables, enforced at the kernel level.
