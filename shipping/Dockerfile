FROM maven:3.9.11
WORKDIR /opt/server
COPY pom.xml .
COPY src ./src 
# to have the exact same src folder structure

RUN mvn clean package 
RUN mv target/shipping-1.0.jar shipping.jar 

# down we giving just cart it will take cart conatiner IP becuse IP will change everytime we going with it
ENV CART_ENDPOINT="cart:8080" \
    DB_HOST="mysql"
CMD ["java","-jar","shipping.jar"]    