This repository will consist of the following folder structure:
.
├── web-app/
├── docker/
│   ├── db/
│   │   └── mariadb/
│   │       └── my.cnf
│   └── server/
│       ├── apache/
│       │   └── sites-enabled/
│       │       └── site.conf
│       ├── php/
│       │   └── php.ini
│       └── Dockerfile
└── .env

*****************************************************************************************************************************************************************

About the Dockerfile:
1. Content of our local folder web-app will be considered a volume mapped to /var/www/html, which is the project root. 

2. Note that here we are copying the entire folder contents so that users can make changes to their scripts without disturbing the Dockerfile thereby .

3. At project's root is a '.env' file copied 

*****************************************************************************************************************************************************************

Configurations:

There are some recommended configurations for PHP and MariaDB in /docker/server/php/php.ini and /docker/db/mariadb/my.cnf, respectively.

*****************************************************************************************************************************************************************

The commands used to build and run the docker image are as follows respectively:
1. docker build -t blexr-php:latest .             ....(Assuming this command to be executed where Dockerfile is present)

2. docker run -i --rm --name blexr-cont -p 80:80 blexr-php:latest

where..
  -t = tag for image to be built
  
  -i = interactive mode
  
  --rm = remove the container as soon as it stops
  
  -p = specifying the port
