# Builder stage
FROM golang:1.22-alpine AS builder

WORKDIR /app
COPY . .

RUN CGO_ENABLED=0 go build -o server

# Final stage
FROM alpine:latest

WORKDIR /root/
COPY --from=builder /app/server .

EXPOSE 8001

CMD ["./server"]
