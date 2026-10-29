# Журнал изменений

## 2026-10-28

- Репозиторий подготовлен к публикации на GitHub.
- Версии образов зафиксированы (Nextcloud 25, ONLYOFFICE 7.2, Snipe-IT v6.0.10, BookStack 26.5.4, Stirling 0.36.6, Uptime Kuma 1.23.16, Homarr 0.15.10, Portainer 2.20.3).
- Секреты вынесены в `.env`, в репозитории — только `.env.example`.
- Добавлены `README.md`, `docs/`, `.gitignore`, `LICENSE`.

## 2026-09-25

- Добавлен Stirling PDF.
- Настроен OCR на русском языке (`rus.traineddata`).
- Настроен лимит размера файла (`SYSTEM_MAXFILESIZE`).

## 2026-09-23

- Настроена глобальная ротация логов Docker (`/etc/docker/daemon.json`, 10 МБ × 3 файла).
- Добавлен BookStack (база знаний).
- Добавлен Homarr (дашборд) и Portainer (управление Docker).

## 2026-09-08

- Развёрнут Snipe-IT (учёт IT-оборудования).
- Устранены проблемы с подключением к БД (ожидание готовности MySQL).

## 2026-09-04

- Развёрнут Nextcloud + ONLYOFFICE в Docker.
- Настроены Group folders для общих папок.
- Отключены публичные ссылки (API публикации) в целях безопасности.
- Отключено автообновление Nextcloud (`NEXTCLOUD_UPDATE=0`).