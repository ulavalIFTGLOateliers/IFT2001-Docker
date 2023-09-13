FROM rust:latest AS build
WORKDIR /app
COPY . .
RUN cargo build --release

FROM debian:bullseye-slim
RUN apt update; apt install -y libpq-dev
WORKDIR /app
COPY --from=build /app/target/release/rust_api ./rust_api
ENV DATABASE_URL=postgres://postgres:postgres@db
CMD ./rust_api
