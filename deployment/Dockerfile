FROM golang:1.22.4

ENV GOOSE_MIGRATION_DIR="/app/migrations"

RUN go install github.com/pressly/goose/v3/cmd/goose@v3.20.0

WORKDIR /app

COPY ./migrations ./migrations

ENTRYPOINT ["/bin/bash", "-c"]

CMD ["goose postgres \"host=$DB_HOST port=$DB_PORT user=$DB_USER password=$DB_PASSWORD dbname=$DB_NAME sslmode=prefer\" up"]
