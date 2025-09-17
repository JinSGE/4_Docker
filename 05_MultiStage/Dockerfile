# FROM golang:1.8 베이스 이미지가 커서 아래로 변경
# FROM golang:alpine 

# 멀티 스테이지 빌드 사용
FROM golang:alpine AS builder
WORKDIR /go/src/app
COPY main.go .

# alpine 이미지 사용시 사용해야하는 코드
RUN go mod init 
RUN go build -o webserver .

# FROM alpine
FROM scratch
WORKDIR /app
COPY --from=builder /go/src/app/ /app/

CMD ["./webserver"]

# 719(golang:1.8) -> 303(golang:alpine) -> 
# 16.4(멀티 스테이지 빌드 - alpine) -> 8.04 (멀티 스테이지 빌드 - scratch)