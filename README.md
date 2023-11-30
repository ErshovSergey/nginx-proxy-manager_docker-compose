# nginx-proxy-manager_docker-compose  
Запустить контейнер  
```docker-compose up --build -d --remove-orphans --force-recreate && docker-compose logs -f```  
Для получения контейров RSA после запуска скопировать letsencrypt.ini в /path/to/DOCKER_DATA/nginx-proxy-manager/letsencrypt/ и перезапросить выпуск сертификата (по мотивам https://just-4.fun/blog/howto/letsencrypt-rsa-keys/).  
## Решение проблем  
Если не получается новый сертификат и в логах есть ошибка  
_Another instance of Certbot is already running_  
### Решение  
в контейнере остановить все процессы certb  
```docker exec -it container_name  /bin/bash```  
```ps -ef | grep certb```  
```kill <process id from prev. command>```  

### Увеличение количества worker_connections  
Создать файл _/data/nginx/custom/events.conf_.  
со строкой  
```worker_connections 10240;```
