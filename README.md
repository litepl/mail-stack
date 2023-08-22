# Description
This stack uses PostgreSQL database as source for user data.
NFS server is required as stack is prepared to be run on Docker Swarm.

# Volumes
| NFS export |Description |
|-------------------------------|-----------------------------|
|/mailstack/mail|mailboxes storage directory
|/mailstack/clam-db|ClamAV DB storage directory
|/mailstack/amavisd-config|Amavisd configuration directory
|/mailstack/amavisd-spool|Amavisd spool directory
|/mailstack/amavisd-dkim|Amavisd DKIM directory with the key
|/mailstack/dovecot-config|Dovecot configuration directory
|/mailstack/postfix-config|Postfix configuration directory
|/mailstack/postfix-spool|Postfix spool directory

You can find example files in **configs** directory.
