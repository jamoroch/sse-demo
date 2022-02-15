FROM node:lts-alpine as build

WORKDIR /dashboard

COPY ./package*.json /app

RUN npm install
COPY . .
RUN npm build

FROM nginx:stable-alpine

COPY ./nginx/nginx.conf /ect/nginx/conf.d/default.conf
COPY --from=build /app/build /usr/share/nginx/html
