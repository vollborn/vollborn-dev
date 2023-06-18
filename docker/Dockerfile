# build
FROM node:20-alpine AS build

COPY ./ /app
WORKDIR /app

RUN npm install && npm run build

# web server
FROM nginx:alpine AS web

COPY --from=build /app/dist /usr/share/nginx/html
