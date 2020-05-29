FROM openjdk:8-jdk

WORKDIR /work

COPY . .

EXPOSE 8080

RUN ./mvnw package

ENTRYPOINT ["java"]

CMD ["-jar", "./target/docker-example-1.1.3.jar"]
