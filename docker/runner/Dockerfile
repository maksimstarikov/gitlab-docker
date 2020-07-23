FROM gitlab/gitlab-runner:latest

MAINTAINER Max Starikov <maxim.starikov@gmail.com>

RUN apt-get update && \
    apt-get install -y php7.2 php7.2-cli php7.2-xml php7.2-pdo php7.2-mysqli \
                       php7.2-gd php7.2-mbstring php7.2-curl php7.2-zip \
                       composer \
                       iputils-ping net-tools

COPY conf/ssh /home/gitlab-runner/.ssh
RUN chown gitlab-runner -R /home/gitlab-runner/.ssh
