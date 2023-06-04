Thanks to: https://www.youtube.com/watch?v=klj6xMUIei4&t=372s
Github: https://github.com/ionghitun/tutorial

## About this Laravel template with docker

# Need this to connect to the DB
https://github.com/sanchezgregory/mysqldocker

# To get in to the page: 127.0.0.1
add a new line to the /etc/hosts -> 127.0.0.1	testapp.local.com # change app by the app name
using: Replace in Files... (right click on root project) testapp -> new_name

# execute this command
cp -r testConnection html (with this you can test DB connection is ok and the docker itself)

# Try enter
Get in to the page: testapp.local.com and you can see the phpinfo() page and the connection to the DB

# Now...
You can clone your laravel app into html folder, and you can re-use the .env existing file for the new projects .env keeping some important variables for the docker itself 

# Clone project only like this: From root docker project
git clone git@github.com:name/project.git html

# Ready config for redis since .env.example
After you see local env is mounted, Go to inside docker and run:
    composer install
    copy .env.example .env 
    php artisan key:generate
    npm install (only if needed)
    npm run build (only if needed)
    php artisan storage:link (filesystem is public)
    composer require laravel/horizon   (for queues)
    php artisan horizon:install        (testapp.local.com/horizon)
    php artisan migrate
    
# Linking to  Mysql5.7 or 8.0 
see: https://github.com/sanchezgregory/mysqldocker

# xdebug
Can start using xdebug using this method = http://testapp.local.com/?XDEBUG_SESSION_START=1
