# Linux Application Server Project

This readme describes all the modifications made to the standard Lightsail Ubuntu machine to accomplish the "Linux Server Configuration" project.

## Virtual Host Information

IP: 13.58.250.189

SSH port: 2200

User: grader

Hosted application URL: http://ec2-13-58-250-189.us-east-2.compute.amazonaws.com/catalog

## Installed Software

The following packages were installed with apt-get:

* apache2
* apache2-dev
* postgresql
* python3-pip
* git

The following packages were installed with pip:

* mod_wsgi
* psycopg2
* Flask_HTTPAuth
* passlib
* requests
* Werkzeug
* httplib2
* Flask
* SQLAlchemy
* google_api_python_client

## Configuration

* The apache server was set to host our application, so we had to change the file "/etc/apache2/sites-available/000-default.conf".

* The database "catalog" was created in Postgree and also the user "cataloger" and all permisions were given to "cataloger" on "catalog".

* The user "grader" was created and given SSH access.

* Root access using SSH was disabled in "/etc/ssh/sshd_config"

* The firewall was set using "ufw" and incoming connections were allowed only for the ports "2200", "80" and "123".

* Some changes were made to the "Item Catalog" project to use "Postgree" as the database and also to the Google credentials to enable access and redirection to the Amazon server.

## References

Some very useful links were used while setting the server:

* [Flask and Apache integration](http://flask.pocoo.org/docs/0.12/deploying/mod_wsgi/)
* [Pip locale error](https://stackoverflow.com/questions/14547631/python-locale-error-unsupported-locale-setting)
* [SQLAlchemy and Postgree autoincrementing issue](https://stackoverflow.com/questions/40280158/postgres-sqlalchemy-auto-increment-not-working?rq=1)
