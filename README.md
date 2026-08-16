# Doctrine Extra Skeleton

Advanced Nette and Doctrine project skeleton with Nettrine and Contributte integrations.

## Requirements

- PHP 8.4 or newer
- [Composer](https://getcomposer.org/)
- `make` for the provided development commands
- Docker Compose for the container stack

## Native quick start

Before running `make build`, start a local PostgreSQL service with the credentials tracked in `config/local.neon.dist`: host `localhost`, database `doctrine`, user `doctrine`, and password `doctrine`.

```bash
composer create-project contributte/doctrine-extra-skeleton acme
cd acme
make project
make build
make dev
```

Composer creates `config/local.neon` from `config/local.neon.dist`. The default local configuration uses a PostgreSQL database on `localhost` named `doctrine`, with user and password `doctrine`.

> **Warning:** `make build` drops the current schema, then runs migrations and loads fixtures.

The development server listens on <http://localhost:8000>. The default route renders the Basic presenter, including the books, categories, and tags loaded by the fixtures.

## Docker Compose

Start the stack with:

```bash
docker compose up
```

The application is available at `http://localhost` and `https://localhost`; Adminer is available at `http://localhost:8081`. The PostgreSQL service is internal to the Compose network and uses database, user, and password `contributte`.

For Compose, update `config/local.neon` to use host `database` and the tracked Compose credentials: database, user, and password `contributte`. The PHP container installs dependencies, runs migrations, and loads fixtures at startup.

## Development

```bash
make qa       # coding standard and static analysis
make tests    # Nette Tester suite
make cs       # coding standard check
make csf      # fix coding standard issues
make phpstan  # static analysis
make coverage # generate coverage.xml
```
