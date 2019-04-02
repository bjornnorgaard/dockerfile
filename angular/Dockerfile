FROM node:10.15 AS BUILD
WORKDIR /app

COPY package.json /app
RUN npm i

COPY . /app
RUN npm run build

FROM nginx:1.15.10-alpine
COPY --from=BUILD /app/dist/angular /usr/share/nginx/html
