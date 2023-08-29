# Utiliza una imagen base de Nginx
FROM nginx:latest

# Copia los archivos de tu página web al directorio de Nginx en el contenedor
COPY ./creative-studio/public_html /usr/share/nginx/html

# Expone el puerto 80 del contenedor para que la aplicación sea accesible
EXPOSE 80

# Comando para iniciar Nginx en primer plano (no se detiene)
CMD ["nginx", "-g", "daemon off;"]
