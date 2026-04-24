# Assignment Instruction
First Steps:

1. Clone base Debian server VM

2. Use the cloned VM

3. Change VM hostname → webserver

4. Recreate SSH Server keys

5. Install Web server (Apache or Nginx)

 

Then, configure NFT tables, block all traffic with the exception:

- Input: SSH and HTTP

- Output: DNS, HTTP and HTTPS

After checking that the configuration is correct, make the rules persistent.

Submit the file with the rules.