FROM node:12.11.1-alpine as angular
WORKDIR /home/app
COPY ./package*.json .
RUN npm install
COPY . .
RUN npm run build

FROM nginx:alpine
WORKDIR /usr/share/nginx/html
COPY --from=angular /home/app/dist/frontend .
EXPOSE 80