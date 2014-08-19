#PHP Hybrid SPA

####Description
This project is meant to be used as a hybrid AJAX application for PHP. It is based on SLIM php and Twig template engine.

####Features
- Twig Templates
- Grunt task runner to compile client code
- Paths are determined by a json file that is read both by grunt and SLIM.
- Coming Soon - Frontend skeleton application to get you started.


####Apache Set Up

#####Hosts File
Add this to your hosts file

```127.0.0.1       local.hybrid-php.com```

#####VHost Config for Windows

```
<Directory "absolute_path_to_project/app">
    Options Indexes FollowSymLinks
    AllowOverride all
    Order allow,deny
    Allow from all
    Require all granted
</Directory>

<VirtualHost 127.0.0.1:80>
    ServerName local.hybrid-php.com
    DocumentRoot "absolute_path_to_project/app"
</VirtualHost>

```

#####VHost Config for MAMP
- Make sure *httpd-vhosts.conf* is included in your configuration file:
  - In */Applications/MAMP/conf/apache/httpd.conf*, search for "Virtual hosts" and unccomment the line *Include /Applications/MAMP/conf/apache/extra/httpd-vhosts.conf*
- Then add the following to *Include /Applications/MAMP/conf/apache/extra/httpd-vhosts.conf*:

```
<VirtualHost *>
    DocumentRoot "/Applications/MAMP/htdocs"
    ServerName localhost
</VirtualHost>

<VirtualHost *>
    DocumentRoot "/path_to_project/app"
    ServerName local.hybrid-php.com
</VirtualHost>

```

`*`*NOTE*: The first entry above is to maintain the reference to your default localhost location set by MAMP


####Initialization
- npm install
  - You may encounter problems with imagemin because its lame on Windows... and Mavericks?
- bower install


####Commands

- grunt bower - copies all of the JS dependencies for bower from *bower_components* to */src/vendor/js/*
- grunt or grunt dev - Build for development
- grunt dist - Build for production

