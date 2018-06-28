FROM tomcat:8.0

ADD spring-webapp/target/springwebapp.war /usr/local/tomcat8/webapps/

RUN apt-get update && apt-get install -y vim
RUN apt-get update && apt-get install -y python
RUN apt-get update && apt-get install -y openssh-server

RUN sed -i 's/PermitRootLogin without-password/PermitRootLogin yes/' /etc/ssh/sshd_config

EXPOSE 8080
EXPOSE 22

CMD /usr/local/tomcat/bin/startup.sh && service ssh restart && /bin/bash
