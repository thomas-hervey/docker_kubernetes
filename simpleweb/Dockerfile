# ORDER MATTERS! For example, copying at different times affects what is copied

# Specify a base image
# in this case, a specific node installation
# (alpine which is baisc and stripped down. I don't think this is the same as the alpine OS)
FROM node:alpine

# save files into another folder
WORKDIR /usr/app

#  copy the package.json file, if there are changes, the npm install will run, otherwise it wont
COPY ./package.json ./

# Install some dependencies
RUN npm install

# copy local files into container (from root to container root)
COPY ./ ./

# Default command
CMD ["npm", "start"]