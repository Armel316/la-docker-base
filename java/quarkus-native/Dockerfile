FROM quay.io/quarkus/ubi-quarkus-native-image:23.1 AS build
WORKDIR /project
COPY . .
RUN ./mvnw package -Pnative -DskipTests

FROM scratch
WORKDIR /app
COPY --from=build /project/target/*-runner application
EXPOSE 8080
ENTRYPOINT ["./application"]