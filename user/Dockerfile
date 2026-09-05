FROM node:20.0-alpine3.16 AS builder
WORKDIR /opt/server
COPY *.js .
COPY package.json .
RUN npm install





FROM node:20.0-alpine3.16
RUN addgroup -S roboshop && adduser -S roboshop -G roboshop
COPY --from=builder --chown=roboshop:roboshop /opt/server /opt/server
ENV REDIS_URL='redis://redis:6379' \
    MONGO="true" \
    MONGO_URL="mongodb://mongodb:27017/users"
USER roboshop
CMD ["node" , "server.js"]














# FROM node:20
# WORKDIR /opt/server
# COPY *.js .
# COPY package.json .
# RUN npm install
# ENV REDIS_URL='redis://redis:6379' \
#     MONGO_URL="mongodb://mongodb:27017/users"
# CMD ["node" , "server.js"]