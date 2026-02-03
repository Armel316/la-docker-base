FROM gcr.io/distroless/java21-debian12
ENV JAVA_OPTS="-XX:MaxRAMPercentage=65"
COPY app.jar /app.jar
USER nonroot
ENTRYPOINT ["java","-jar","/app.jar"]