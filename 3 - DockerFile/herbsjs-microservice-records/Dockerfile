FROM node:18

ENV SERVER_PORT=3109
ENV MYSQL_HOST=mysql-service
ENV MYSQL_PORT=3306
ENV MYSQL_USER=root
ENV MYSQL_PASSWORD=root
ENV MYSQL_DATABASE=testedb
ENV GLOBAL_PREFIX=/records/v1

RUN mkdir -p /app
WORKDIR /app

COPY . /app
RUN npm install
EXPOSE 3109

CMD ["npm", "start"]

#docker build -t herbsjs-records .

#docker run -it -p 3109:3109 herbsjs-records

#docker tag herbsjs-records reinaldopadua/herbsjs-records
#docker push reinaldopadua/herbsjs-records 