# Doctrine Extra Skeleton

Advanced Nette and Doctrine project skeleton with Nettrine and Contributte integrations.

## Requirements

- PHP 8.4 or newer
- [Composer](https://getcomposer.org/)
- `make` for the provided development commands
- Docker Compose for the container stack

## Create a project

```bash
composer create-project contributte/doctrine-extra-skeleton acme
cd acme
make project
make build
make dev
```

Composer creates `config/local.neon` from `config/local.neon.dist`. The default local configuration uses a PostgreSQL database on `localhost` named `doctrine`, with user and password `doctrine`.

`make build` drops the current schema, runs migrations, and loads fixtures. The development server listens on `http://localhost:8000`.

## Docker Compose

Start the stack with:

```bash
docker compose up
```

The application is available at `http://localhost` and `https://localhost`; Adminer is available at `http://localhost:8081`. The PostgreSQL service is internal to the Compose network and uses database, user, and password `contributte`.

For Compose, set `parameters.database.host` in `config/local.neon` to `database` and use the Compose database credentials. The PHP container installs dependencies, runs migrations, and loads fixtures at startup.

## Development

```bash
make qa       # coding standard and static analysis
make tests    # Nette Tester suite
make cs       # coding standard check
make csf      # fix coding standard issues
make phpstan  # static analysis
make coverage # generate coverage.xml
```
