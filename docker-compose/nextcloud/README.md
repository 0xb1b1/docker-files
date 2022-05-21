# Nextcloud

## What is Nextcloud?
Nextcloud is a powerful self-hosted cloud storage service. It has plugin and DAV support and many other perks to help its users manage their files and tasks.

## FAQ
Q: There are three docker-compose files. Which one do I choose?
A: Here's a brief desctiption for each one of them:
  - `docker-compose.yml` provides you with one open HTTP port - and that's it. You have to use your own reverse proxy (nginx, for example) to set up HTTPS.
  - `docker-compose-https.yml` runs Nginx reverse proxy container along with Nextcloud - and accepts certificates in `./proxy/certs`
  - `docker-compose-https-letsencrypt.yml` runs Nginx reverse proxy and LetsEncrypt contaners along with Nextcloud and generates LE certificates on startup
 
Q: How do I start a specific `docker-compose` file?
A: You have two ways of achieving this.
The simplest option would be rename `docker-compose.yml` to something like `docker-compose.orig.yml` and then, again, rename the configuration you chose to `docker-compose.yml`.
The second option is to execute `docker-compose` with the `-f` flag, followed by the name of the file you chose. For example, `docker-compose -f docker-compose-https-letsencrypt.yml up -d` will read and execute instructions from `docker-compose-https-letsencrypt.yml`.

