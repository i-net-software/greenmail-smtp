# greenmail smtp
A simple docker image with SMTP, IMAP and a webmail based up on greenmail and docker_smtp. This composition is dedicated to development environements because it will accept all emails and never relay to internet. 

This composition will launch 2 services in 2 images:
* WEBMAIL service on port *8080*, run by `apache2` and `roundcube` at http://127.0.0.1:8080/webmail/
* SMTP+s, IMAP+s (and if needed POP3+s) services, run by `greenmail`

SMTP will accept all emails and creates separate accounts for each mail received. The username and password are set to the email address of the created account.

Mail clients, such as the WEBMAIL service can authenticate with these credentials to check on the mails.

Usage :

```bash
git clone https://github.com/i-net-software/greenmail-smtp.git
cd greenmail-smtp/
# docker-compose build # (optional step)
docker-compose up
```

Then you can configure apps to send emails to local port 25 and you can read received emails on http://127.0.0.1:8080/webmail/
