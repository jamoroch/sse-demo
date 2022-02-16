FROM node:lts-alpine as build

WORKDIR /frontend

COPY ./package.json /frontend/package.json
COPY ./package-lock.json /frontend/package-lock.json

RUN npm install
COPY . .
RUN npm run build

FROM nginx:stable-alpine

COPY ./nginx/nginx.conf /ect/nginx/conf.d/default.conf
COPY --from=build /frontend/build /usr/share/nginx/html
