FROM eclipse-temurin:21-jre-alpine
RUN addgroup -S app && adduser -S app -G app
ENV JAVA_OPTS="-XX:MaxRAMPercentage=80"
WORKDIR /app
COPY app.jar .
USER app
ENTRYPOINT ["java","-jar","app.jar"]