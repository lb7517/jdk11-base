##### 通过Dockerfile制作jdk11基础镜像，切换成阿里源

* * *
**Dockerfile-base 文件:**

FROM openjdk:11.0.8-jre

RUN sed -i s@/security.debian.org/@/mirrors.aliyun.com/@g /etc/apt/sources.list \
    && sed -i s@/deb.debian.org/@/mirrors.aliyun.com/@g /etc/apt/sources.list \
    && apt-get clean \
	&& apt-get update \
	&& apt-get install -y vim unzip \
	&& ln -sf /usr/share/zoneinfo/Asia/Shanghai /etc/localtime \
    && echo "Asia/Shanghai" > /etc/timezone
