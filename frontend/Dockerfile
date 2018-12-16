# PHASE I (Build Phase)
# install dependencies and build app

# name phase `builder`
FROM node:alpine as builder
# set work directory
WORKDIR '/app'
# copy package.json
COPY package.json .
# install dependencies
RUN npm install
# copy over remaining source code
COPY . .
# build
RUN npm run build


# PHASE II (Run Phase)
# copy build folder and run nginx

FROM nginx
# (NOTE: for developer to read, it doesn't do anything on it's own. However, AWS Elastic Beanstalk looks at exposed instruction and set it as the port for mapped instruction)
EXPOSE 80
# only copy over build folder from the builder phase (where from, where to)
COPY --from=builder /app/build /usr/share/nginx/html

# no need to start up nginx, it will run automatically