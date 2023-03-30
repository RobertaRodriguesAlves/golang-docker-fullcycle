FROM golang:1.20-alpine AS Build

WORKDIR /app
COPY . .
RUN go build -ldflags '-s -w' main.go

FROM scratch

WORKDIR /
COPY --from=Build /app /
ENTRYPOINT [ "./main" ]

