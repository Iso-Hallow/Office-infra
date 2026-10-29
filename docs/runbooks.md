# Runbooks — типовые операции

## Запуск всех сервисов

```bash
for d in ~/office-infra/services/*/; do
  cd "$d" && docker compose up -d
done