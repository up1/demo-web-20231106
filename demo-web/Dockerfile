FROM node:21-alpine3.17 as build01
WORKDIR /app
COPY package*.json .
RUN npm i  
COPY . .
RUN npm run build

FROM nginx:1.21.3-alpine
COPY --from=build01 /app/dist /usr/share/nginx/html

#docker image build -t react-app:1.0 .
#docker container run -d -p 8888:80 react-app:1.0