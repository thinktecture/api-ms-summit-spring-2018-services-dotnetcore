# Build Image
FROM node:9-alpine AS build-env

WORKDIR /usr/app
COPY . .

RUN npm install
RUN npm run build

# Runtime Image
FROM nginx:alpine
COPY --from=build-env /usr/app/dist /usr/share/nginx/html
