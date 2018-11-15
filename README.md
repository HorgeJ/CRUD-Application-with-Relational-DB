# CRUD-Application-with-Relational-DB
This application will be built using PHP, JavaScript, MySQL, HMTL, CSS, and JQuery and will perform the four functions of persistent storage (CRUD)

## Setting Up the Development Server
Using WAMP (Windows, Apache, MySQL and PHP) we can set up an environment for developing dynamic web applications. 

#### Installing XAMPP
XAMPP is the most popular PHP development environment. XAMPP is a completely free, easy to install Apache distribution containing MariaDB, PHP, and Perl. The XAMPP open source package has been set up to be incredibly easy to install and to use.

Download at http://apachefriends.org. Once downloaded and going throug the installer you'll want to keep Apache,
MySQL,  PHP,  and  PHPMyAdmin  checked. Install using the default options.

The  default  ports  assigned  will  normally  be  port  80  for  the  Apache  web  server,  443  for
SSL,  and  3306  for  MySQL

#### Testing Installation
Display  the  default  web  page,  which  will  have  been  saved in  the  server’s  document  root  folder 
Enter  either  of  the  following two  URLs  into  the  address  bar  of  your  browser:

localhost [specifies local computer]
127.0.0.1 

This should greet you with the XAMPP homepage.

#### The Document Root
The document root is the directory where a websites main documents for the domain are stored. It is the url passed to the browser without any paths ex: http://google.com or for your local server http://localhost.

XAMP by default uses 
C://xamp/htdocs

To test that everything is working properly we will create the obligatory 'Hello World' file! 
Using some boilerplate HTML we can create a file hello./html in our root directory

```HTML
<html>
  <head>
    <title> Test Page </title>
  </head>
  <body>
    <h1> Hello World! </h1>
  </body>
</html>
```
quickly test it by visiting: http://localhost.html and we should be greeted by our "Hello World" heading in the browser.
