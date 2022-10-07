FROM centos:7

LABEL version="1.0"
LABEL description="This is an apache image installed in centos"
LABEL author="Jhoan Ortiz S."

RUN yum install -y httpd

WORKDIR /var/www/html/

ENV contenido prueba
RUN echo "${contenido}" > /var/www/html/prueba.html

RUN echo "$(whoami)" > /var/www/html/user1.html

RUN useradd ricardo
USER ricardo
RUN echo "$(whoami)" > /tmp/user2.html

USER root
RUN cp /tmp/user2.html /var/www/html/user2.html

COPY run.sh /run.sh

CMD sh /run.sh
