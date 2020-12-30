FROM openjdk:8-jdk-alpine

RUN apk add bash
COPY wait-for-it.sh /usr/local/bin/
COPY webapi /webapi
RUN cd /webapi && /webapi/gradlew build

ENV JAVA_OPS="-Xms64m -Xmx512m"
ENTRYPOINT exec java $JAVA_OPTS -Djava.security.egd=file:/dev/./urandom -jar /webapi/build/libs/webapi-1.0.0-SNAPSHOT.jar
