FROM node:14-slim AS build

WORKDIR /moringa/devops-04/ip2/ui

COPY ./package.json ./
COPY ./package-lock.json ./

RUN npm install

COPY . .


FROM alpine:3.16.7

WORKDIR /ui

RUN apk update && apk add npm

COPY --from=build /moringa/devops-04/ip2/ui /ui

EXPOSE 3000

CMD [ "npm", "start" ]