FROM node:alpine

WORKDIR /app
COPY package.json .
RUN npm install
COPY index.html /
EXPOSE 8080
CMD [ "node", "-e", "const http = require('http');const fs = require('fs');const server = http.createServer((req, res) => {if (req.url === '/') {fs.readFile('/index.html', (err, data) => {if (err) {res.writeHead(500);res.end('Error loading index.html');} else {res.writeHead(200, {'Content-Type': 'text/html'});res.end(data);}});} else {res.writeHead(404);res.end('Not Found');}});server.listen(8080);" ]
