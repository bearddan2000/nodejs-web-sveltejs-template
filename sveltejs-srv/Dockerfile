FROM node:latest AS build-step
WORKDIR /app
COPY bin .
RUN npm i
RUN npm run build

FROM nginx:latest
COPY --from=build-step /app/public /usr/share/nginx/html
