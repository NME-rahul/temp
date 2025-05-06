# Email

* E-malis are an asynchronous commmunication medium.

<p align="center">
  <img src="https://www.computer-networking.info/1st/html/_images/email-arch.png" />
</p>

**Services**
1. User Agent(mail reader): Local programs that helps read, send and manage emails. can be command based or GUI based.
2. Message Transfer Agent: Run in background o move message from host to destination.

## SMTP

* Mail Transfer protocol, uses to send mail
* Port 25
* Uses TCP

## POP3(Post Office Protocol version 3)

* Mail Access Protocol, pulls the mail from server permamntely(deletes from server).
* Does not maintain state of session.
* USe TCP
* Port 110

## IMAP(Internet Message Access Protocol)

* Mail Access protocol, pull the mails from server.
* Keeps track of message status(read, replied, mark of deletion etc).
* Permits server side search.
* Use TCP
* Port 143


### Web Access
* User agents is a web browser and interacts with mail server via HTTP(as opposes to using SMTP or POP3/IMAP).
* Mail Servers still uses SMTP to talk with each other.
