docker-owncloud
===============

Set your posgresql password to postgres/secrets.yml. Default username is postgres.

	postgres:
	  environment:
	    - POSTGRES_PASSWORD=set_your_password

# Run up docker cluster

	$ sudo docker-compose -f docker-compose-owncloud.yml up -d

# TODO
- HTTPS support
- Collect containers logs

Thanks for https://github.com/tkock/owncloud-docker-compose
