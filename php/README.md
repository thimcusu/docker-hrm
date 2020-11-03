#SET UP LARAVEL FOR PRODUCTION

1. Go to Laravel project directory :
```
	cd /var/www/html/hrm-php
```
2. Pull project to the directory:
```
	git pull	
```
3. Make sure have enviroment file. If not, using the sample file provided: `cp .env.example .env`

4. Install all the dependencies using composer:
```
	composer install
```
5. Generate a new JWT authentication secret key:
```
	php artisan jwt:generate
```
6. Run the database migrations ( **Set the database connection in .env before migrating** ):
```
	php artisan migrate
```
7. Restart nginx:
```
	sudo systemctl restart nginx
```

**Note**: PHP is running in port 8080, check: `/etc/nginx/conf.d/laravel.conf`.

