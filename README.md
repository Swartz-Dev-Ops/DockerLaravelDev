Assumptions:
Docker should be installed.
Composer Should be installed.

Create Directories /mysql /src /nginx (should be created for you)

run 'docker-compose build && docker-compose up -d'

cd to /src and install laravel. 
'composer create-project laravel/laravel .'

-- note: installing with composer should also run 'composer install' in the process to install all dependencies. --

in /src copy .env-example to .env

update .env
DB_CONNECTION=mysql
DB_HOST=mysql
DB_PORT=3306
DB_DATABASE=homestead
DB_USERNAME=homestead
DB_PASSWORD=secret

run migration
'docker-compose exec php php artisan migrate'
data should be created in the /mysql directory.

access laravel at http://localhost:8080

Enjoy!

-- Other Notes
Enable Auth
composer require laravel/ui
php artisan ui vue --auth
docker-compose exec php php artisan migrate
docker-compose exec php php artisan ui:auth
