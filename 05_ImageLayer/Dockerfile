# 베이스 이미지 - 레이어 1
FROM ubuntu

# nginx 생성 - 레이어 2
RUN apt update && apt install -y -q nginx

# 파일 복사 - 레이어 3
COPY index.html /usr/share/nginx/html

# nginx 시작 - 레이어랑 상관 없음.
CMD [ "nginx", "-g", "datemon off;" ]
