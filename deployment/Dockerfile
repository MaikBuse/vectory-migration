FROM golang:1.22.4

ENV GOOSE_DRIVER="postgres"
ENV GOOSE_MIGRATION_DIR="/app/migrations"

RUN go install github.com/pressly/goose/v3/cmd/goose@v3.20.0

WORKDIR /app

COPY ./migrations ./migrations

ENTRYPOINT ["/bin/bash", "-c"]

CMD ["echo $DB_HOST && goose up"]
