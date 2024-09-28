#---------------------------------------------------------------------

FROM ubuntu

# to enter interactive mode while building
ENV DEBIAN_FRONTEND=noninteractive

RUN apt-get update && apt-get install -y openjdk-17-jdk && apt-get install -y maven && apt-get install -y git

WORKDIR /app

RUN git clone https://github.com/spring-projects/spring-petclinic.git

WORKDIR /app/spring-petclinic

RUN ./mvnw package

#COPY target/*.jar app.jar

RUN cp target/*.jar app.jar

EXPOSE 8080

# in CMD "target/*.jar" doesn't work because of the "*" so we coppied the file to app.jar
CMD ["java", "-jar", "app.jar"]

