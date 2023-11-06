FROM node:21-alpine3.17 as build01
WORKDIR /app
COPY package*.json .
RUN npm i  
COPY . .
EXPOSE 3000
RUN npm install pm2 -g
CMD [ "pm2-runtime", "server.js" ]

#docker image build -t demo-node:1.0 .
#docker container run -d -p 3000:3000 demo-node:1.0