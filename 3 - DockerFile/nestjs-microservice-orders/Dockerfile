FROM node:18

ENV SERVER_PORT=3000
ENV MONGODB_HOST=mongodb-service
ENV MONGODB_DATABASE=ordersDB
ENV GLOBAL_PREFIX=microservice-orders/v1
ENV Client_MS_URL=http://records-service:3109/records/v1/Client
ENV Product_MS_URL=http://records-service:3109/records/v1/Product
ENV RABBITMQ_HOST=rabbitmq-service
ENV RABBITMQ_PORT=5672
ENV EXCHANGE_NAME=exchangeOrders
ENV ROUTING_KEY=exchangeOrdersQ
ENV REDIS_HOST=redis=service
ENV REDIS_PORT=6379

RUN mkdir -p /app
WORKDIR /app

COPY . /app

RUN npm install
RUN npm test
RUN npm prebuild
RUN npm build


EXPOSE 3000
ENTRYPOINT npm run start

#docker build -t nestjs-pub-orderss .
#docker run -it -p 3000:3000 nestjs-pub-orders

#docker tag nestjs-pub-orders reinaldopadua/nestjs-pub-orders
#docker push reinaldopadua/nestjs-pub-orders
