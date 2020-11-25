FROM openjdk:14 AS builder
COPY . /usr/src/reactive-backend
WORKDIR /usr/src/reactive-backend
RUN mvn -N io.takari:maven:0.7.7:wrapper && ./mvnw clean package

FROM openjdk:14
COPY --from=builder /usr/src/reactive-backend/target/reactive-web-1.0.0-SNAPSHOT.jar /usr/src/reactive-backend/
WORKDIR /usr/src/reactive-backend
EXPOSE 8080
CMD ["java", "-jar", "reactive-web-1.0.0-SNAPSHOT.jar"]
