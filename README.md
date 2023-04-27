# nginx-proxy-manager_docker-compose  
Запустить контейнер  
```docker-compose up --build -d --remove-orphans --force-recreate && docker-compose logs -f```  
Для получения контейров RSA после запуска скопировать letsencrypt.ini в /path/to/DOCKER_DATA/nginx-proxy-manager/letsencrypt/ и перезапросить выпуск сертификата (по мотивам https://just-4.fun/blog/howto/letsencrypt-rsa-keys/).  
