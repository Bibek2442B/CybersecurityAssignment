# Assignment Instructions

The Importance of Secure Email Communication
The security of communications is very important. Email is one of the most commonly used tools for communication between collaborators, service providers, and clients. Usually, the information exchanged is private or confidential, and its disclosure could result in catastrophic events. Therefore, students are invited to use GPG to enhance the security of their email communication.



## Task Instructions:

Generate a GPG key pair associated with your IPB email account. (My IPB email account is a59441@alunos.ipb.pt.)
Configure the email client to use your IPB email account and their GPG keys.
Task Submission Process:

Send an email. The email should be encrypted with your professor's key and signed with your private key. Attach your public key to this email. The email subject should be [GPG Test].
After receiving your email, the professor will use your public key to encrypt a response and sign that response with his private key.
Lastly, send a confirmation email to the professor, signed and encrypted.
Only if steps 1, 2, and 3 are done correctly will you pass this task. The email should be sent to your shift's professor.

### Hints:

Thunderbird (email client) already has built-in support to GPG.
Double-check that you are signing with your private key and encrypting with the recipient's public key.
Find your professor's GPG key online ;)


Notes:


### Implementation
Install Thunderbird on Ubuntu Workstation
```bash
gpg --full-generate-key
```
* Select RSA and RSA (default).

* Choose a keysize of 4096.

* Enter your Name and IPB Email Address.

*  Crucial: Set a strong passphrase. This protects your private key if your computer is stolen.