FROM node:14-alpine

WORKDIR /app

# Copiamos las dependencias
COPY package.json /app/

# Instalar las dependencias
RUN npm install

COPY . /app/

EXPOSE 3000

CMD ["node", "./scripts/start.js"]


