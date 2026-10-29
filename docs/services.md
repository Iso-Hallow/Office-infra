# Карта сервисов

| Сервис | URL | Порт | Папка | Данные |
|---|---|---|---|---|
| Nextcloud | http://<SERVER_IP>/ | 80 | `nextcloud-onlyoffice/` | `db_data`, `nc_data` |
| ONLYOFFICE | http://<SERVER_IP>:8080/ | 8080 | `nextcloud-onlyoffice/` | — |
| Snipe-IT | http://<SERVER_IP>:8082/ | 8082 | `snipe-it/` | `snipe_db` |
| BookStack | http://<SERVER_IP>:8088/ | 8088 | `bookstack/` | `./bookstack_db` |
| Stirling PDF | http://<SERVER_IP>:8090/ | 8090 | `stirling-pdf/` | `./trainingData`, `./extraConfigs`, `./logs` |
| Uptime Kuma | http://<SERVER_IP>:8086/ | 8086 | `uptime-kuma/` | `./uptime-kuma` |
| Homarr | http://<SERVER_IP>:8085/ | 8085 | `homarr-portainer/` | `./homarr/` |
| Portainer | http://<SERVER_IP>:9000/ | 9000 | `homarr-portainer/` | `portainer_data` |

## Статус-страница

Публичная: http://<SERVER_IP>:8086/status/myoffice
