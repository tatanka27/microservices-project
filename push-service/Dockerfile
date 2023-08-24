FROM openjdk:17-jdk-slim as builder
WORKDIR /app
COPY . .
RUN  ./gradlew bootJar

FROM openjdk:17-jdk-slim
COPY --from=builder /app/build/libs/app.jar /app/

EXPOSE 8080
ENTRYPOINT ["java","-jar","/app/app.jar"]