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

# Upload bigger files

The default maximum file size for uploads is 512MB.

You can increase maximum file size e.g. with following commands:

	$ sudo docker exec --user www-data -i -t dockerowncloud_owncloud_1 /bin/bash
	$ sed -i -- 's/513M/2G/g' .htaccess

or listen php.ini and nginx:

	$ sudo docker exec --user www-data -i -t dockerowncloud_owncloud_1 /bin/bash
	$ sed -i.bak '/upload_max_filesize/d' ./.htaccess
	$ sed -i.bak '/post_max_size/d' ./.htaccess

Notice that those options are not persistence! It effects only for running container, so when you upgrade or remove it all changes has gone.

# TODO
- Collect containers logs

Thanks for https://github.com/tkock/owncloud-docker-compose
