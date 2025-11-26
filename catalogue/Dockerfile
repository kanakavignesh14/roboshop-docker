FROM node:20
WORKDIR /opt/server
COPY package.json .
COPY *.js .
RUN npm install
ENV MONGO="true" \
    MONGO_URL="mongodb://mongodb:27017/catalogue"
    #"mongodb://<MONGODB-SERVER-IPADDRESS>:27017/catalogue"
    # I just gave conatiner name automatically it will take IP
    # docker will assign IP to container by bridge network
CMD  ["node", "server.js"]   # starting node