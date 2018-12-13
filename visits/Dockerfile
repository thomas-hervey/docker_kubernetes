# base image
FROM node:alpine

# determine where to save the app
WORKDIR '/app'

# copy files from local folder to docker container
COPY package.json .
RUN npm install
COPY . .

# run startup commands
CMD ["npm", "start"]