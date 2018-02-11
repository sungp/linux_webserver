# linux_webserver

This repo contains the instruction (this README file) on how to connect to linux server that's running a standalone webapp for storing and displaying arbitrary catalog items. The following list contains relevant information on how to connect to the server

## Logging to webserver
* the webserver is being hosted by AWS available at following location
  * ip: 54.191.121.93
  * hostname: c2-54-191-121-93.us-west-2.compute.amazonaws.com
  * public key file: LightsailDefaultPrivateKey-us-west-2.pem (available with the repo)
* Logging to the webserver using the public key by issuing following command at the promp
  * ssh grader@54.191.121.93  -p 2200 -i LightsailDefaultPrivateKey-us-west-2.pem

## Using the webapp 
* enter the following address in the browser's address bar
  * http://ec2-54-191-121-93.us-west-2.compute.amazonaws.com/
* you can edit the items (add or delete) by logging in.  Otherwise, you can freely browse items and their description without logging in. 

## Software installed
* apache2
* python-pip
* libapache2-mod-wsgi
* postgresql
* python_psycopg2
* python libraries
 * flask
 * sqlalchemy
 * oauth2client
 * requests

## Configuration made
* grader user has been added and added sudoer's list
* configure login to only use key-based login
* root ssh has been disabled
* ssh port has been reconfigured to 2200
* all system package has been updated
* filrewall has been configured only allow 2200, 80, and 123
* installed and configured catalog app under /var/www/catalog
* installed postregsql and used database_setup.py under /var/www/catalog to initialize
