Thanks to: https://www.youtube.com/watch?v=klj6xMUIei4&t=372s
Github: https://github.com/ionghitun/tutorial

## About this Laravel template with docker

# Need this to connect to the DB
https://github.com/sanchezgregory/mysqldocker

# To get in to the page: 127.0.0.1
add a new line to the /etc/hosts -> 127.0.0.1	app.local.com # change app by the app name
using replace in file (right click on root project) app -> new name

# If you see this error:
The directory named as part of the path /var/www/storage/logs/horizon.log does not exist in section 'program:horizon'
After complete load docker, you must uncomment lines 26 and 27 and 39, 40 from docker/php/supervisord.conf

# Try enter
Get in to the page: app.local.com and you can see the phpinfo() page and the connection to the DB

# Now...
You can clone your laravel app into html folder, and you can re-use the .env existing file for the new projects .env keeping some important variables for the docker itself 

# Ready config for redis since .env.example
After you see local env is mounted, Go to inside docker and run:
    composer install
    copy .env.example .env 
    php artisan key:generate
    npm install (only if needed)
    npm run build (only if needed)
    php artisan storage:link (filesystem is public)
    composer require laravel/horizon   (for queues)
    php artisan horizon:install        (app.local.com/horizon)
    php artisan migrate
    
# Linking to  Mysql5.7 or 8.0 
see: https://github.com/sanchezgregory/mysqldocker


#xdebug
Can start using xdebug using this method = http://app.local.com/?XDEBUG_SESSION_START=1
