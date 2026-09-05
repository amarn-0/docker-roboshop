FROM python:3.9
WORKDIR /opt/server
COPY payment.ini .
COPY payment.py .
COPY rabbitmq.py .
COPY requirements.txt .
ENV CART_HOST="cart" \
    CART_PORT="8080" \
    USER_HOST="user" \
    USER_PORT="8080" \
    AMQP_HOST="rabbitmq"
CMD ["uwsgi", "--ini" , "payment.ini" ]
