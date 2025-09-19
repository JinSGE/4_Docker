# 베이스 이미지
FROM quay.io/centos/centos:stream9

# 패키지 설치
RUN yum -y install vsftpd && yum clean all

# 파일 복사
COPY vsftpd.conf.template /etc/vsftpd/vsftpd.conf

# 저장소 설정 및 파일 복사 및 실행
VOLUME /var/ftp/pub
COPY WelcomeToMyFTPServer.txt /var/ftp/pub/

EXPOSE 21 20

ENTRYPOINT ["/usr/sbin/vsftpd"]

