FROM openjdk:latest
EXPOSE 8080

COPY ./spring-example-project/ /usr/src/thirteen
WORKDIR /usr/src/thirteen
RUN ./mvnw package
CMD java -jar ./target/docker-example-1.1.3.jar
