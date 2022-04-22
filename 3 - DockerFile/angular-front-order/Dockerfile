FROM node:16.13.0 as build-stage

RUN mkdir -p /build
WORKDIR /build

COPY . /build

RUN npm install
RUN npm run build

FROM nginx 

WORKDIR /usr/share/nginx/html

RUN rm -rf * 

COPY --from=build-stage /build/dist/* .

EXPOSE 80

CMD ["nginx", "-g", "daemon off;"]

#docker build -t frontend-orders .
#docker run -it -p 8080:80 frontend-orders

#docker tag frontend-orders reinaldopadua/frontend-orders
#docker push reinaldopadua/frontend-orders 