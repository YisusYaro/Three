FROM node:lts AS builder

RUN npm install -g @angular/cli@13.0.0

WORKDIR /usr/src/app

COPY ./ /usr/src/app/

# install phaser

RUN npm install 

RUN ng build



FROM nginx:alpine

COPY ./nginx/default.conf /etc/nginx/conf.d/default.conf 

COPY --from=builder /usr/src/app/dist/clarity /usr/share/nginx/html