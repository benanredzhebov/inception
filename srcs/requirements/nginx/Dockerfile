#creates a minimalNginx container. Uses Alpine Linux as the base image for a lightweight and secure ervironment
#updates Alpine's package repository, upgrade existing packages, installs Nginx without caching unnecessary package files
#opens port 443
#runs Nginx in the foreground(doesn't exit immediately)
FROM alpine:3.21.2
RUN	apk update && apk upgrade && apk add --no-cache nginx
EXPOSE 443
CMD ["nginx", "-g", "daemon off;"]
