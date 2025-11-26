FROM node:20

WORKDIR /opt/server

COPY package.json .
COPY *.js .

RUN npm install

# Environment variables
ENV MONGO=true \
    MONGO_URL="mongodb://mongodb:27017/catalogue"
# Note: "mongodb" is the container name — Docker resolves it automatically to its IP

# Start the Node application
CMD ["node", "server.js"]
