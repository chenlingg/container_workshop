#select the base image
FROM node:latest

LABEL name="northwindapp"
LABEL maintainer="cl@nus.edu.sg"

ENV DB_HOST=mydb
ENV DB_PORT=3306
ENV APP_PORT=3000
ENV APP_DIR=/app

WORKDIR ${APP_DIR}

ADD package-lock.json .
ADD package.json .
ADD main.js .
ADD public public
ADD views views
ADD config config

#install dependencies
RUN npm install
#expose the port 3000
EXPOSE ${APP_PORT}
#start the app
ENTRYPOINT [ "node", "main.js" ]
