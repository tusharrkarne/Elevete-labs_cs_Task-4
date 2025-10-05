# Elevete-labs_cs_Task-4
Setup and Use a Firewall on Kali Linux with UFW.

Task 4: Setup and Use a Firewall on Kali Linux with UFW.

✅ Step-by-Step Process
1.	Install and Enable UFW
-	$sudo apt update
-	$sudo apt install ufw -y        # Install UFW if not already installed
 

-	$sudo ufw enable                	# Enable firewall
 

-	$sudo ufw status verbose            # Show current firewall status and rules
 
2.	Check Default Policies
Use if Default Policies not set
-	$sudo ufw default deny incoming
-	$sudo ufw default allow outgoing

3.	List current firewall rules
-	$sudo ufw status numbered
-	Output shows all rules in effect (numbered for easy deletion later).

4.	Block Inbound Traffic on Port 23 (Telnet)
-	$sudo ufw deny 23/tcp
-	$sudo ufw status numbered
-	Now port 23/TCP is blocked.

5.	Test the Rule
-	$nc -vz localhost 23
-	Result: connection refused or blocked.


6.	Allow SSH (Port 22)
To avoid locking yourself out:
-	$sudo ufw allow 22/tcp
-	$sudo ufw status numbered

-	This ensures remote SSH is still accessible.

-	

7.	Remove the Test Rule
When finished, remove the Telnet block rule:
-	$sudo ufw delete deny 23/tcp

Or delete by rule number:
-	$sudo ufw status numbered


