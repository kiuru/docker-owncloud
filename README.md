docker-owncloud
===============

Set your posgresql password to postgres/secrets.yml. Default username is postgres.

	postgres:
	  environment:
	    - POSTGRES_PASSWORD=set_your_password

# Run up docker cluster

	$ sudo docker-compose -f docker-compose-owncloud.yml up -d

# Get access to running owncloud container and print its version number:

	$ sudo docker exec --user www-data -i -t dockerowncloud_owncloud_1 /bin/bash
	$ ./occ --version

# TODO
- HTTPS support
- Collect containers logs

Thanks for https://github.com/tkock/owncloud-docker-compose
