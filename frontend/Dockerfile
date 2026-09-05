FROM nginx
RUN rm -rf /usr/share/nginx/html/* && \
    rm -rf /etc/nginx/conf.d/* && \
    rm -rf /etc/nginx/*
COPY static/ /usr/share/nginx/html/
COPY nginx.conf /etc/nginx/nginx.conf
