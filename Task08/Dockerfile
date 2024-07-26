FROM ubuntu

# to enter interactive mode while building
ENV DEBIAN_FRONTEND=noninteractive

RUN apt-get update && apt-get install -y openjdk-17-jdk && apt-get install >

WORKDIR /app

RUN git clone https://github.com/spring-projects/spring-petclinic.git

WORKDIR /app/spring-petclinic

RUN ./mvnw package

RUN cp target/*.jar app.jar

EXPOSE 8080

CMD ["java", "-jar", "app.jar"]
