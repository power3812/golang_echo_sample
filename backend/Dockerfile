FROM golang:1.17-bullseye

WORKDIR /backend
ENV GO111MODULE on

COPY go.mod .
COPY go.sum .

RUN go mod download
COPY . ./backend

# COPY  ./main.go /backnd/main.go
RUN go get -u github.com/cosmtrek/air && \
    go build -o /go/bin/air github.com/cosmtrek/air

EXPOSE 5000
CMD ["air", "-c", ".air.toml"]

