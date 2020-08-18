# select base image
FROM node:11.15
# app dir
WORKDIR /usr/src/app
# install app dependencies
COPY package*.json ./
RUN npm ci 
# include app source
COPY . .
# apis port number
EXPOSE 8080
# default start behavior
CMD [ "npm", "run", "prod" ]
