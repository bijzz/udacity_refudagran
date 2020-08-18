# multi stage build
# https://docs.docker.com/develop/develop-images/multistage-build/

# (1)
# select base image
FROM beevelop/ionic:latest AS ionic
# app dir
WORKDIR /usr/src/app
# install app dependencies
COPY package*.json ./
RUN npm ci
# include app source
COPY . .
# build
RUN ionic build

# (2)
# select base image
FROM nginx:alpine
COPY --from=ionic  /usr/src/app/www /usr/share/nginx/html



