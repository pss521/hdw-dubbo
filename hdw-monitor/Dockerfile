# hdw-monitor docker配置
FROM frolvlad/alpine-oraclejdk8

MAINTAINER TuMinglong (tuminglong@126.com)

VOLUME /tmp

ENV PROJECT_HOME /home/project
ENV TOMCAT_HOME /home/tomcat/webapps
ENV OUTPUT_HOME /output

RUN mkdir -p "$PROJECT_HOME" && mkdir -p "$OUTPUT_HOME" && mkdir -p "$TOMCAT_HOME"

ADD hdw-monitor.jar /home/project/hdw-monitor.jar

WORKDIR /home/project

RUN sh -c 'touch  /hdw-monitor.jar'

ENV JAVA_OPTS=""
ENTRYPOINT [ "sh", "-c", "java $JAVA_OPTS -Djava.security.egd=file:/dev/./urandom -jar /home/project/hdw-monitor.jar" ]

EXPOSE 8444

docker run -it -d --name hdw-monitor -p8444:8444 -v /output:/output hdw-monitor:v1
