Help me do this HTTPS Task. I have cloned the base debian server. I also have the Ubuntu workstation

# HTTPS Task

### Pre-tasks steps

- Clone base Debian server VM

- Use the cloned VM

- Change VM hostname -> ipbusername_webserver

- Example user ei9524 -> ei9524_webserver

- Recreate SSH Server keys

 

## HTTP and HTTPS Configuration

- Install Nginx

- Create a directory named protected on the document root of the
Nginx server

- Create an index.html file inside that directory with your student
email

- Configure HTTPS on Nginx

- Configure Nginx to request simple authentication to access the
protected directory in both HTTP and HTTPS

 

## Tests

- On the Ubuntu VM (or your host machine) install Wireshark

- Use Wireshark to capture the traffic between Ubuntu (or your host machine) and the
Debian Server

- Using the browser to test the access to the protected directory thought
HTTP and HTTPS

- Analyse the capture on the Wireshark:

- Find the user and password in plain text during the access to
the protected directory via HTTP. Take a screenshot of that info
on the Wireshark window

- Show that accessing the protected directory via HTTPS the
traffic is cyphered. Take a screenshot of that info on the
Wireshark window.

## Submission

Submit the two screenshots as proof of your work.

