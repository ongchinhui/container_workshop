FROM node:latest

LABEL name="northwindapp"
LABEL maintainer="ongchinhui"

ENV DB_HOST=mydb 
ENV DB_PORT=3306
ENV DB_USER=root 
ENV DB_PASSWORD=changeit 

ENV APP_PORT=3000 
ENV APP_DIR=/app 
ENV APP_DEFAULT_CITY='singapore'

WORKDIR ${APP_DIR}

#ADD . .
ADD main.js .
ADD package.json .
ADD package-lock.json .
ADD config config
ADD public public
ADD views views

RUN npm install 

#HEALTHCHECK --interval=15s --timeout=10s \
#	CMD curl -f http://localhost:${APP_PORT}/health || exit 1

EXPOSE ${APP_PORT}

ENTRYPOINT [ "node", "main.js" ]

CMD [ "" ]
