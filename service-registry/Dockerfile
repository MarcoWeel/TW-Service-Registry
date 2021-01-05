FROM maven:3.6.0-jdk-11-slim AS build
VOLUME /tmp
COPY src tmp/*/src
COPY pom.xml /tmp
RUN mvn -f tmp/pom.xml clean package
ARG JAR_FILE=tmp/target/*.jar
COPY ${JAR_FILE} app.jar
ENTRYPOINT ["java","-jar","/app.jar"]

