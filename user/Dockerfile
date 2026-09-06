FROM node:20.0-alpine3.16 AS builder
WORKDIR /opt/server
COPY *.js .
COPY package.json .
RUN npm install


FROM node:20.0-alpine3.16
WORKDIR /opt/server
RUN addgroup -S roboshop && adduser -S roboshop -G roboshop
ENV REDIS_URL='redis://redis:6379' \
    MONGO="true" \
    MONGO_URL="mongodb://mongodb:27017/users"
COPY --from=builder --chown=roboshop:roboshop /opt/server /opt/server
USER roboshop
CMD ["server.js"]
ENTRYPOINT ["node"]





# FROM node:20
# WORKDIR /opt/server
# COPY *.js .
# COPY package.json .
# RUN npm install
# ENV REDIS_URL='redis://redis:6379' \
#     MONGO_URL="mongodb://mongodb:27017/users"
# CMD ["node" , "server.js"]