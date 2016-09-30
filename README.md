# aljp Django Skeleton

The motivation for this is project is a better foundation to quickly get a django project started

# Whats included?

Vagrant and Docker for the local development environment

Vagrant works easily across different operating systems (like windows)

Within Vagrant we run the web server, postgresql server, redis server, celery worker server, celery beat server, rabbitmq message queue server, and a mailcatcher server

These servers are run as docker containers within the vagrant machine and orchestrated through the docker-compose.yml file, inspired by [12Factor](https://12factor.net/) [Dev/Production parity](https://12factor.net/dev-prod-parity)

# Caveats

Windows users... if you want to use any python management commands locally with a postgresql database, you will need to install psycopg2 from binaries found online, there are issues installing it from pip.

Laptop users... this setup is quite heavy, if you allocate less than 2cpu cores and 2gb of ram (defined in the Vagrantfile) then it may fail to build, it works fine on my macbook pro though

# Contributing

Feel free to contribute to the repo by making a fork and submitting a pull request documenting your changes. 

If you notice any issues please feel free to create an issue in the issues tab.