#SET UP LARAVEL FOR PRODUCTION

1. Go to Laravel project directory :
```
	cd /var/www/html/hrm-fe
```
2. Pull project to the directory:
```
	git pull	
```
3. Install all the dependencies:
```
	npm install
```
5. Build application, run script:
```
	npm run build
```
6. Restart nginx:
```
	sudo systemctl restart nginx
```

**Note**: REACT is running in port 80(default), check(don't change): 
```
	cat /etc/nginx/nginx.conf
```
 

