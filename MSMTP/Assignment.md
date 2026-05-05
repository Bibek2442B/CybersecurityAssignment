Help me do this HTTPS Task. I have cloned the base debian server. I also have the Ubuntu workstation
# MSMTP & Logwatch Task

### Pre-tasks steps

- Create clone VM from the base debian one

- Use the cloned VM

- Change VM hostname -> a59441_task4 

- Recreate SSH Server keys

Create a test account on Gmail to be used during these tests

Don't forget to activate the option in Gmail account to support the use of insecure
applications


## MSTMP

- Install msmtp-mta

- Configure to use the test account previously created Gmail account

- Send a test email from the machine to your email. You can use the command mail.

 

## Logwatch

- Install Logwatch

- Configure Logwatch:

  * Mail From and To to the test email

  * Range = yesterday

  * Detail = Low

  * Service = All

  * With daily reports activated

- Test Logwatch by running it manually:

  * Detail = high

  * Range = all

  * Service = all

  * Send an email to the test email account created

## Submission
Upload the email received