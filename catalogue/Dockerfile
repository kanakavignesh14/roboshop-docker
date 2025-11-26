#Thing's	Included in node:20?	Notes
#1.Base OS (Linux)	✅	Debian/Alpine
#2.Node.js 20 software	✅	Pre-installed
#3.npm	✅	Comes with Node
#4.Your code	❌	You add using COPY
#5.Node modules

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
