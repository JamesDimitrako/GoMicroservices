# Dockerfile References: https://docs.docker.com/engine/reference/builder/

# Start from golang:1.12-alpine base image
FROM golang:1.15.8-buster 

# Add Maintainer Info
LABEL maintainer="Dimitris Dimitrakopoulos"

COPY . /httpapi 
WORKDIR /httpapi

ENV GO111MODULE=on

RUN CGO_ENABLED=0 GOOS=linux go build -o httpapi 

# Download all dependencies. Dependencies will be cached if the go.mod and go.sum files are not changed
RUN go mod download

# Command to run the executable
CMD ["go","run","main.go"]

