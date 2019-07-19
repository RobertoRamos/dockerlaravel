# Docker para Laravel 5.6 >

Llegar e instalar repo de laravel con PHP 7.2 Iniciar con docker-compose up -d

--------------------------------------------------------------------------------

# Para virtualBox:

- Agregar los dominios en archivo hosts de Windows
- Asignar los puertos de salida en :Configuracion > Red > Avanzadas > Reenvio de puertos:

  - Agregar 80 y 3306 (apache/mysql)

--------------------------------------------------------------------------------

# Para Linux:

Realizar el cambio de UID y GID con los de tu cuenta. Agregar los dominios en /etc/hosts apuntando a 127.0.0.1

--------------------------------------------------------------------------------

# Para todos reemplazar:

- docker-compose.yml.example >> docker-compose.yml
- .env.example >> .env
- nginx/nginx_default.conf >> nginx/nginx.conf (solo como lectura)
