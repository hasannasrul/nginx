# Nginx Webserver

To install nginx in debian based use

```sudo apt install nginx -y```

To install nginx in arch based

```sudo yum install nginx -y```

To check the status of nginx

```sudo systemctl status nginx```

To restart the nginx 

```sudo systemctl restart nginx```

To check the syntax of config file use

```nginx -t```

### Nginx configurations

Config Files are available at locations

```/etc/nginx/```

nginx.conf file is the main configuration file for Nginx and is located in the top-level directory of Nginx configuration, which is typically /etc/nginx/. This file contains the global settings for the Nginx server, such as the user and worker processes, server blocks, and other directives that control how Nginx functions

*Other import folders present in ```/etc/nginx`` are*
    1. sites-available
    2. sites-enabled
    3. conf.d

*1. sites-available*

We usually put our configuration files (individual config files which ends with .conf) at this location.
These files contains different blocks of configuration. These files through symlink is used in sites-enabled
to create symlink use this command

```ln -s /etc/nginx/sites-available/myfile.conf /etc/nginx/sites-enabled/```

*2. sites-enabled*

We only placed those files in this directory which are required to serve to the client. By default this directory 
is included in nginx.conf file. which tells nginx to use configuration files from here.

*3. conf.d*
Same function as sites-enabled. One directory can be excluded in nginx.conf (check include directive with path to these folders and remove one of them)

#### Misc. 

One other Important folder is present at 

```/var/www/html```

From this folder we can serve static files to the client.

#### logs

By default logs are setup at this location

```/var/log/nginx/```

name of the logs file are
1. access.log
2. error.log

We can configure log files location and name in nginx.conf or our separate config files in (conf.d, sites-available)