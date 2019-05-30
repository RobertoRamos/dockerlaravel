# Docker para Laravel 5.6 >
Llegar e instalar repo de laravel con PHP 7.2

Iniciar con docker-compose up -d

Para virtualBox hay que asignar los puertos de salida:
 * Configuracion > Red > Avanzadas > Reenvio de puertos:
 	* Agregar 80 y 3306 (apache/mysql)
 
Reemplazar:

> docker-compose.yml.example >> docker-compose.yml
> .env.example >> .env
> nginx/nginx_default.conf >> nginx/nginx.conf
 
