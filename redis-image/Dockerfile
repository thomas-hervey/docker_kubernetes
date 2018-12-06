# Use an existing docker image as a base
# apline is a slim linux OS
FROM alpine

# Download an install a dependency
# uses Apache package manager to install redis
RUN apk add --update gcc
RUN apk add --update redis

# Tell the image what to do when it starts as a container
# tell the terminal to run redis-server
CMD ["redis-server"]