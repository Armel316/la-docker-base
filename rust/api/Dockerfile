FROM rust:1.77 AS build
WORKDIR /app
COPY Cargo.toml Cargo.lock ./
RUN cargo fetch
COPY . .
RUN cargo build --release

FROM debian:bookworm-slim
WORKDIR /app
COPY --from=build /app/target/release/app .
EXPOSE 8080
CMD ["./app"]
