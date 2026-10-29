# Runbooks — типовые операции

## Запуск всех сервисов

```bash
for d in ~/office-infra/services/*/; do
  cd "$d" && docker compose up -d
done
```

## Остановка всех сервисов

```bash
for d in ~/office-infra/services/*/; do
  cd "$d" && docker compose down
done
```

## Проверка статуса конкретного сервиса

```bash
cd ~/office-infra/services/<сервис>
docker compose ps
```

## Логи

```bash
docker compose logs --tail=50
```

## Перезапуск

```bash
docker compose restart
```

## Полное пересоздание (данные сохраняются!)

```bash
docker compose down        # БЕЗ -v
docker compose up -d
```

## Типовые проблемы

### «Доступ через недоверенный домен» (Nextcloud)

```bash
docker exec -u 33 -it <app_container> php occ config:system:set trusted_domains 1 --value=*
```

### «Приложение ONLYOFFICE недоступно»

1. Проверить, что контейнер ONLYOFFICE в статусе `Up`.
2. Открыть `http://<SERVER_IP>:8080/` — должна быть страница Document Server.
3. В настройках Nextcloud указать `http://<SERVER_IP>:8080/`.

### Контейнер в `Restarting`

```bash
docker compose logs --tail=50
```

Чаще всего — БД ещё не готова. Подождать и перезапустить приложение:

```bash
docker compose restart <app>
```

## Резервное копирование

```bash
docker run --rm \
  -v nextcloud-offline_db_data:/data \
  -v /backup:/backup \
  alpine tar czf /backup/db_data.tar.gz -C /data .
```

## Ротация логов Docker

Файл `/etc/docker/daemon.json`:

```json
{
  "log-driver": "json-file",
  "log-opts": { "max-size": "10m", "max-file": "3" }
}
```
