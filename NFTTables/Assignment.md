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



A new version (/tmp/tmp.PP53BwC2iY) of configuration file /etc/ssh/sshd_config is available, but the version installed currently has been locally modified.
What do you want to do about modified configuration file sshd_config?
  install the package maintainer's version
  keep the local version currently installed
  show the differences between the versions
  show a side-by-side difference between the versions
  show a 3-way difference between available versions
  do a 3-way merge between available versions
  start a new shell to examine the situation




  ```sh
#!/usr/sbin/nft -f

flush ruleset

table inet filter {

    chain input {
        type filter hook input priority 0;
        policy drop;

        # Allow loopback
        iif lo accept

        # Allow established connections
        ct state established,related accept

        # Allow SSH (port 22)
        tcp dport 22 accept

        # Allow HTTP (port 80)
        tcp dport 80 accept
    }

    chain output {
        type filter hook output priority 0;
        policy drop;

        # Allow loopback
        oif lo accept

        # Allow established connections
        ct state established,related accept

        # Allow DNS (port 53)
        udp dport 53 accept
        tcp dport 53 accept

        # Allow HTTP (port 80)
        tcp dport 80 accept

        # Allow HTTPS (port 443)
        tcp dport 443 accept
    }

    chain forward {
        type filter hook forward priority 0;
        policy drop;
    }
}
  ```






#!/usr/sbin/nft -f

flush ruleset

table inet filter {
        chain input {
                type filter hook input priority filter;
        }
        chain forward {
                type filter hook forward priority filter;
        }
        chain output {
                type filter hook output priority filter;
        }
}