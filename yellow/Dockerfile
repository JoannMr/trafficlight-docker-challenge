FROM node:17.0-alpine3.14

WORKDIR /app

COPY package*.json ./

RUN apk add --no-cache npm=7.17.0-r0 && npm install

COPY app.js ./
COPY index.pug favicon.ico ./views/

EXPOSE 80

CMD ["node", "app.js"]
