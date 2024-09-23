FROM openjdk:17-jdk-alpine

EXPOSE 8080

WORKDIR /app

COPY ./spring-petclinic/build/libs/spring-petclinic-3.3.0.jar app.jar

CMD java -jar app.jar
