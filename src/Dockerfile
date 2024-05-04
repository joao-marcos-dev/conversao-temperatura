FROM ubuntu
ARG NODE_MAJOR=20
# Actualiza el sistema e instala las dependencias necesarias
RUN apt-get update && apt-get install -y \
    curl \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/

# Descarga e instala Node.js LTS
RUN curl -sL https://deb.nodesource.com/setup_lts.x | bash -
    RUN apt-get install -y nodejs

# Verifica la instalación de Node.js y npm
RUN node --version && npm --version 

# Define el directorio de trabajo dentro del contenedor
WORKDIR /app

COPY . .
RUN npm install
ENTRYPOINT [ "node", "server.js" ]



