FROM gradle:8-jdk21 AS build
WORKDIR /build
COPY build.gradle settings.gradle ./
RUN gradle dependencies
COPY src ./src
RUN gradle build -x test

FROM eclipse-temurin:21-jre-alpine
ENV JAVA_OPTS="-XX:MaxRAMPercentage=75 -XX:InitialRAMPercentage=50"
WORKDIR /app
COPY --from=build /build/build/libs/*.jar app.jar
EXPOSE 8080
ENTRYPOINT ["java","-jar","app.jar"]