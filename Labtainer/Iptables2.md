Labtainers iptables2 is a cybersecurity lab exercise focused on configuring a Linux firewall to restrict network traffic, specifically allowing only SSH and HTTP connections while dropping other protocols.  The lab utilizes the iptables utility to manage packet filtering rules within a Docker-based virtual environment.

To complete the tutorial and lab tasks, follow these general steps based on the provided context:

Start the Lab: Open your terminal, navigate to the labtainer-student directory, and execute the command labtainer iptables2. Wait for the client and firewall terminal windows to open. 
Configure Firewall Rules: In the firewall terminal, edit the iptables configuration file (often using sudo nano /etc/iptables.rules or a similar script in the lab directory). You must add rules to:
Allow SSH traffic (typically on port 22).
Allow HTTP traffic (on port 80).
Drop or Reject all other incoming traffic to ensure only the specified services are accessible. 
Apply and Test: Save the configuration and run the provided script (e.g., sudo ./example or sudo iptables-restore) to apply the rules. Use tools like nmap from the client terminal to verify that only ports 22 and 80 are open, while others are filtered. Use tcpdump or tail -f /var/log/iptables.log to observe dropped packets.
Snort Integration (Optional/Related): Some variations of this lab sequence may include a snort component to demonstrate intrusion detection.  You may need to configure Snort rules in /etc/snort/rules/local.rules to detect suspicious traffic or Nmap scans.
Submission: Take screenshots of your configuration changes, the successful filtering of traffic, and the log entries. Compile these into a report and save the generated lab file from the labtainer_xfer folder for submission. 
For specific course requirements, always refer to the PDF tutorial instructions linked within the lab terminal, as grading criteria (such as specific file names like sniff.pcapng for other labs) may vary by institution. 







3 Lab Tasks
3.1 Explore
The Wireshark utility is installed on the firewall. Use it to view network traffic through the firewall, and to debug your firewall rules. 
Start it from the firewall terminal:
wireshark &
Then select the eth0 interface.
On the client terminal use the nmap utility to list (some of the) open ports on the server:
nmap server
Use wget to confirm that the server response to HTTP requests:
wget server &
Confirm an ssh service if offered – you need not login when prompted, just use ctrl C to exit once you
get a response from the server.
ssh server
Finally, confirm that telnet is offered (again, no need to login):
telnet server
Observe the traffic in wireshark, making note the source IP addresses and the destination ports used by the
clients when connecting to the server
3.2 Use iptables to limit traffic
The iptables utility is installed on the “firewall” component. Use it to prevent the firewall from forwarding
any traffic to the server other than SSH and HTTP.
You may reference and experiment with the example firewall script that is on the firewall component in
the home directory. To run the example fw.sh script, use:
sudo ./example_fw.sh
View the content of the script to understand what it does. Consider putting your iptables commands in a
script so it is easy to test and reconfigure the iptables if you restart the lab.
Note the last line in the example fw.sh script directs iptables to log dropped packets. You can view
these from one of the firewall terminal tabs via:
tail -f /var/log/iptables.log
After modifying your iptables configuration, use the applications on the client to demonstrate that the
firewall only allows the desired traffic. Watch the traffic in wireshark to see that the TCP handshake fails
when attempting to connect to filtered ports.
Use nmap to confirm the proper configuration:
nmap server

3.3 Open new service port
The client computer includes a wizbang program that you must now allow to send traffic to the server.
Run the program from the client, and observe which port it attempts to use within wireshark:
./wizbang
Then alter your iptables to allow this service. After adjusting your iptables, confirm that you can run the
wizbang program successfully. Also, again use nmap to confirm the proper configuration
nmap server