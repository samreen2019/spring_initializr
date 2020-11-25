FROM openjdk:8 AS builder
COPY . /usr/src/spring_initializr
WORKDIR /usr/src/spring_initializr
RUN ./mvnw clean package

FROM openjdk:8
COPY --from=builder /usr/src/spring_initializr/target/demo-0.0.1-SNAPSHOT.jar /usr/src/spring_initializr/
WORKDIR /usr/src/spring_initializr
EXPOSE 8080
CMD ["java", "-jar", "demo-0.0.1-SNAPSHOT.jar"]
