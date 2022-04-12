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

About the Dockerfile:
1. Content of our local folder web-app will be considered a volume mapped to /var/www/html, which is the project root. 
2. Note that here we are copying the entire folder contents so that users can make changes to their scripts without disturbing the Dockerfile thereby .
3. At project's root is a '.env' file copied 


The commands used to build and run the docker image are as follows respectively:
1. docker build -t blexr-php:latest .
2. docker run -d -p 80:80 blexr-php:latest
