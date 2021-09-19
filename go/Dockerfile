# syntax=docker/dockerfile:1

# Set the baseImage to use for subsequent instructions. FROM must be the first instruction.
FROM golang:1.17-alpine

# The absolute or relative path to use as the working directory. Will be created if it does not exist.
WORKDIR /app

# Copy files or folders from source to the dest path in the image's filesystem.
COPY go.mod ./
COPY go.sum ./

# Execute any commands on top of the current image as a new layer and commit the results.
RUN go mod download

COPY *.go ./

RUN go build -o /thienry-fullcycle

# Define the network ports that this container will listen on at runtime.
EXPOSE 8080

# Provide defaults for an executing container. If an executable is not specified, then ENTRYPOINT must be specified as well. There can only be one CMD instruction in a Dockerfile.
CMD [ "/thienry-fullcycle" ]
