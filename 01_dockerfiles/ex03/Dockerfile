FROM ubuntu
MAINTAINER matheme <matheme@student.le-101.fr>

EXPOSE 80 443 22
RUN apt-get update -y
RUN apt-get upgrade -y
RUN apt-get install -y curl openssh-server ca-certificates postfix
RUN apt install -y tzdata

RUN curl -sS https://packages.gitlab.com/install/repositories/gitlab/gitlab-ce/script.deb.sh | bash
RUN apt install gitlab-ce
ENTRYPOINT (/opt/gitlab/embedded/bin/runsvdir-start &) && gitlab-ctl reconfigure && gitlab-ctl start && tail -f /dev/null

#how to run it
#docker build -t ex03 .
#docker run --rm -it -p 8080:80 -p 8022:22 -p 8443:443 ex03
