#Thing's	Included in node:20?	Notes
#1.Base OS (Linux)	✅	Debian/Alpine
#2.Node.js 20 software	✅	Pre-installed
#3.npm	✅	Comes with Node
#4.Your code	❌	You add using COPY
#5.Node modules

FROM node:20
 # this node image come with base os, node software and npm packages  
 WORKDIR /opt/server
 COPY package.json .
 COPY server.js .
 RUN npm install
ENV REDIS_HOST="redis"  \
    CATALOGUE_HOST="cata" \
    CATALOGUE_PORT="8080"
CMD ["node", "server.js"]   
   