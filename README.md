# PHP-FPM - Xdebug - Nginx - MariaDB

This skeleton intends to simplify the creation of environments for PHP, Laravel & Symfony applications.\
You feel free to modify the files to generate images and containers that meet your needs.\
In the <b>.ENV</b> file almost all parameters are configured. Also, you can change the image versions from Docker Hub, and set versions of programs, ports, and more.

![some](https://img.shields.io/badge/DEFAULT_VERSIONS-ab530f)
![php](https://img.shields.io/badge/PHP_FPM-8.1-brightgreen.svg)
![xdebug](https://img.shields.io/badge/Xdebug-3.2.2-brightgreen.svg)
![nginx](https://img.shields.io/badge/nginx-1.25-brightgreen.svg)
![mariadb](https://img.shields.io/badge/MariaDB-11.1.1-brightgreen.svg)
![docker](https://img.shields.io/badge/Docker-compose-brightgreen.svg)

#
### The skeleton uses:

* [Docker](https://www.docker.com) - [Docker Compose](https://docs.docker.com/compose) - [Dockerfile](https://docs.docker.com/engine/reference/builder/)
* [PHP](https://php.net) Hypertext Preprocessor
* [Nginx](https://nginx.org) webserver
* [MariaDB 11.1.2](https://mariadb.org) Database
* [Composer](https://getcomposer.org) to create your project easily
* [Xdebug](https://xdebug.org) for debug

#
### Additionals Installations

* To add <b>NODE-JS</b> set "<b>yes</b>" in the .ENV file
* To add <b>Symfony-CLI</b> set "<b>yes</b>" in the .ENV file
* You can add more installations and configurations, and after that put the Bash script in the Dockerfile.

#
### Directory Structure

* ![some](https://img.shields.io/badge/docker-%20files%20to%20configure%20the%20environment.%20[%20Dockerfile,%20nginx.conf,%20xdebug.ini,%20php_overrides.ini%20]-e1e5e6)

* ![some](https://img.shields.io/badge/project-%20this%20is%20the%20root%20directory%20for%20your%20application-e1e5e6)

* [![some](https://img.shields.io/badge/vscode-%20replacement%20file%20when%20you%20create%20a%20launch.json%20.%20<<%20Click%20Here%20to%20see%20how%20to%20build%20it>>-e1e5e6)](https://code.visualstudio.com/docs/editor/debugging#_launch-configurations)

* ![some](https://img.shields.io/badge/xdebug-%20here%20Xdebug%20saves%20the%20logs.%20Usually,%20you%20will%20need%20to%20empty%20this%20directory%20to%20free%20space-e1e5e6)

* ![some](https://img.shields.io/badge/mariadb-%20this%20directory%20is%20created%20when%20you%20build%20the%20skeleton%20first%20time-e1e5e6)

* ![some](https://img.shields.io/badge/.env-%20configuration%20variables%20of%20environment-e1e5e6)

* ![some](https://img.shields.io/badge/docker_compose_yml-%20settings%20of%20docker%20services-e1e5e6)

#
### Build the Skeleton

* You just need to execute the command [ <b>docker compose up</b> ] [ optionals <b>-d</b> & <b>--build</b> ]

#
### Notes & Examples

* You need to delete the directory /project/<b>public</b> before install some framework
* After that execute the next commands inside the /project directory as you need
* Laravel [ <b>composer create-project laravel/laravel .</b> ]
* Symfony [ <b>composer create-project symfony/skeleton:"x.x.*" .</b> ] [ after optional <b>composer require webapp</b> ]
* Symfony CLI if is installed [ <b>symfony new . --version="x.x.*" --webapp</b> ]
  
#

<br/>

$${I \space\space HOPE \space\space THIS \space\space HELPS \space\space YOU. \space\space ENJOY \space\space IT \space !}$$
