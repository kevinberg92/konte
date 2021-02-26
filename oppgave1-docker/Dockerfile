FROM maven:3.6-jdk-11 as builder
WORKDIR /app
COPY pom.xml .
COPY src ./src
COPY index.html .
RUN mvn package -DskipTests

FROM adoptopenjdk/openjdk11:alpine-slim
WORKDIR /app
COPY --from=builder /app/target/*.jar /app/application.jar
ENTRYPOINT ["java","-jar","/app/application.jar"]

