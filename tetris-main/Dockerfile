# Use the official Node.js 14 image
FROM node:14

# Establecer directorio de trabajo
WORKDIR /app

# Copiar archivos de dependencias
COPY package*.json ./

# Instalar dependencias
RUN npm install express

# Copiar el resto de la aplicación
COPY . .

# Puerto expuesto por la aplicación
EXPOSE 3000

# Comando para iniciar la aplicación
CMD ["node", "server.js"]
