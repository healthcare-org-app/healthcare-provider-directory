# provider-directory

provider-directory — domain: providers

- **Port:** 8206
- **Language:** Python 3.11 + Flask
- **Database:** `providers` (Postgres, table `provider_directory`)
- **Event bus:** Kafka

## API

| Method    | Path                       |
|-----------|----------------------------|
| GET       | `/api/provider_directory/`          |
| POST      | `/api/provider_directory/`          |
| GET       | `/api/provider_directory/<id>`      |
| PUT/PATCH | `/api/provider_directory/<id>`      |
| DELETE    | `/api/provider_directory/<id>`      |
| GET       | `/health`                  |
| GET       | `/ready`                   |

## Events

**Publishes:** (none)
**Subscribes:** (none)

## HTTP peer dependencies

- `providers-service`
- `specialties-service`
- `credentialing-service`
- `audit-log-service`

## Local dev

```bash
pip install -e ../../libs/py-healthcare-common
pip install -r requirements.txt
cp .env.example .env
(cd ../../infra && docker compose up -d postgres kafka kafka-init)
python -m app.main
```

## Tests

```bash
pytest
```
