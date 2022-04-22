FROM node:18

ENV RABBITMQ_HOST=rabbitmq-service
ENV RABBITMQ_QUEUE=exchangeOrders
ENV ORDER_SERVICE_HOST=http://order-service:3000/microservice-orders/v1/orders

RUN mkdir -p /app
WORKDIR /app

COPY . /app
RUN npm install

ENTRYPOINT  node ./receive.js

#docker build -t node-sub-orders .
#docker run -it node-sub-orders

#docker tag node-sub-orders reinaldopadua/node-sub-orders
#docker push reinaldopadua/node-sub-orders 