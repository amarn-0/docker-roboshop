FROM node:20.0-alpine3.16 AS builder
WORKDIR /opt/server
COPY *.js .
COPY *.json .
RUN npm install




FROM node:20.0-alpine3.16
WORKDIR /opt/server
RUN addgroup -S roboshop && adduser -S roboshop -G roboshop 
COPY --from=builder --chown=roboshop:roboshop /opt/server /opt/server
ENV REDIS_HOST="redis" \
    CATALOGUE_HOST="catalogue" \
    CATALOGUE_PORT="8080"
USER roboshop
CMD ["server.js"]
ENTRYPOINT ["node"]

# FROM node:20
# WORKDIR /opt/server
# COPY *.js .
# COPY *.json .
# RUN npm install
# ENV REDIS_HOST="redis" \
#     CATALOGUE_HOST="catalogue" \
#     CATALOGUE_PORT="8080"
# CMD ["node" , "server.js"]
