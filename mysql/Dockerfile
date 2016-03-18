#################################################################
# Dockerfile to build mysql to solve the [ERROR] InnoDB problem
# Based on mysql:lastet
#################################################################

FROM mysql
MAINTAINER ky.storm <ky.storm@163.com>

COPY run.sh /
RUN chmod 755 /run.sh

CMD /run.sh