FROM haskell:9.0-buster
RUN stack setup --install-ghc
WORKDIR /app
COPY . .
RUN stack build
CMD ["stack", "run"]
