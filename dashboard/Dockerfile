FROM node:lts-alpine as build

WORKDIR /dashboard

COPY ./package.json /dashboard/package.json
COPY ./package-lock.json /dashboard/package-lock.json

RUN npm install
COPY . .
RUN npm run build

FROM nginx:stable-alpine

COPY ./nginx/nginx.conf /ect/nginx/conf.d/default.conf
COPY --from=build /dashboard/build /usr/share/nginx/html
