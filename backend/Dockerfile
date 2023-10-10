FROM node:14-slim AS build

WORKDIR /moringa/devops-04/ip2/server

COPY ./package.json ./
COPY ./package-lock.json ./

RUN npm install

COPY . .


FROM alpine:3.16.7

WORKDIR /server

RUN apk update && apk add --update nodejs

COPY --from=build /moringa/devops-04/ip2/server /server

EXPOSE 5000

CMD [ "node", "server.js" ]