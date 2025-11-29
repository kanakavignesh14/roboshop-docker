FROM python:3.9 as builder
WORKDIR /opt/server
COPY payment.ini *.py requirements.txt .
#storing all packges in custom folder and giving to final imgae 
RUN pip3 install --prefix=/install  -r requirements.txt


FROM python:3.9.25-alpine3.21 
WORKDIR /opt/server
RUN addgroup -S roboshop && adduser -S roboshop -G roboshop && \
    chown -R roboshop:roboshop /opt/server
EXPOSE 8080
LABEL project="roboshop" \
      Trianer="SIVA"
ENV CART_HOST="cart" \
    CART_PORT="8080" \
    USER_HOST="user" \
    USER_PORT="8080" \
    AMQP_HOST="rabbitmq" \
    AMQP_USER="roboshop" \
    AMQP_PASS="roboshop123"

# check classmate note for more onfo related /usr/local/bin we we used here details.
COPY --from=builder /install /usr/local/bin
COPY --chown=roboshop:roboshop payment.ini *.py requirements.txt .
USER roboshop
CMD ["uwsgi","--ini","payment.ini"]  

#FROM python:3.9
#WORKDIR /opt/server

#COPY payment.ini .
#COPY payment.py .
#COPY rabbitmq.py .
#COPY requirements.txt .

#RUN pip3 install -r requirements.txt

#ENV CART_HOST="cart" \
 #   CART_PORT="8080" \
  #  USER_HOST="user" \
   # USER_PORT="8080" \
   # AMQP_HOST="rabbitmq" \
   # AMQP_USER="roboshop" \
   # AMQP_PASS="roboshop123"

#CMD ["uwsgi","--ini","payment.ini"]    