FROM node:21-alpine3.17 as build01
WORKDIR /app
COPY package*.json .
RUN npm i  
COPY . .
EXPOSE 3000
CMD [ "npm", "start" ]

#docker image build -t demo-node:1.0 .
#docker container run -d -p 3000:3000 demo-node:1.0