#Thing's	Included in node:20?	Notes
#1.Base OS (Linux)	✅	Debian/Alpine
#2.Node.js 20 software	✅	Pre-installed
#3.npm	✅	Comes with Node
#4.Your code	❌	You add using COPY
#5.Node modules

FROM mysql:8.0
ENV MYSQL_ROOT_PASSWORD="RoboShop@1"
COPY db/ /docker-entrypoint-initdb.d
