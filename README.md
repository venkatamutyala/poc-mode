# poc-mode

This project sets up a PostgreSQL database along with pgAdmin using Docker Compose. It is designed for easy local development and testing.

## Project Structure

```
poc-mode
├── docker-compose.yaml
├── README.md
└── pgadmin/
    └── servers.json
```

## Services

### PostgreSQL

- A PostgreSQL database is set up with a local volume for persistent data storage.
- The default password for the PostgreSQL user is `yolo1234`.

### pgAdmin

- pgAdmin is included to provide a web-based interface for managing the PostgreSQL database.
- It is pre-configured to connect to the PostgreSQL database using the `servers.json` file.

## Getting Started

1. **Clone the repository** (if applicable):
   ```bash
   git clone <repository-url>
   cd poc-mode
   ```

2. **Start the services**:
   ```bash
   docker-compose up -d
   ```

3. **Access pgAdmin**:
   - Open your web browser and go to `http://localhost:8080`.
   - Log in using the email `admin@admin.com` and the password `yolo1234`.

4. **Verify the Pre-configured Server**:
   - The PostgreSQL server (`PostgresDB`) should already appear in pgAdmin under the "Servers" group.
   - If it does not appear, ensure the `servers.json` file is correctly mounted and formatted.

## Stopping the Services

To stop the services, run:
```bash
docker-compose down
```

## To Stop and Recreate Everything

```bash
docker-compose down --volumes
docker-compose up --build --force-recreate --renew-anon-volumes
```

## Notes

- Ensure Docker and Docker Compose are installed on your machine.
- The local volume will persist data even when the containers are stopped or removed.
- The `servers.json` file is mounted to pre-configure the PostgreSQL server in pgAdmin.