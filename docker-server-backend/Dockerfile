# Etapa 1: Construir la aplicación de React
FROM node:14 as build

# Establece el directorio de trabajo en /app
WORKDIR /app

# Instala las dependencias
RUN npm install -g create-react-app

# Crea la aplicación React-Admin
RUN npx create-react-app my-react-admin-app

# Ingresa al directorio de la aplicación
WORKDIR /app/my-react-admin-app

# Instala react-admin (u otras dependencias si es necesario)
RUN npm install react-admin

# Compila la aplicación de React
RUN npm run build

# Etapa 2: Servir la aplicación con Nginx
FROM nginx:alpine

# Copia los archivos de la aplicación compilada desde la etapa anterior al directorio de Nginx
COPY --from=build /app/my-react-admin-app/build /usr/share/nginx/html

# Expone el puerto 80 para que la aplicación sea accesible
EXPOSE 80

# Comando para iniciar Nginx en primer plano (no se detiene)
CMD ["nginx", "-g", "daemon off;"]
