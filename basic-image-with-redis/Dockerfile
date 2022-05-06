# base image:alpine is used for its small size
FROM alpine

# packages or dependencies
# apk: aprivation for: Alpine linux package manager
RUN apk add --update redis

# commands to run on image
CMD [ "redis-server" ]