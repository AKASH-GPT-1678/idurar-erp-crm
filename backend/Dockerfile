FROM node:22-alpine

WORKDIR /app

COPY package*.json ./

RUN npm install

COPY  src /app/src
COPY .pretti* ./
COPY .eslintrc.js ./






EXPOSE 8888

CMD [ "node", "src/server.js" ]
