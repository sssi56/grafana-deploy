## Видео
https://rutube.ru/video/6929cf2036b160df9d5ad63e483a690f/?r=plwd

## Нагрузочное тестирование с ab:

```
ab -k -c 5 -n 20000 'http://localhost:8080/' & \
ab -k -c 5 -n 2000 'http://localhost:8080/status/400' & \
ab -k -c 5 -n 3000 'http://localhost:8080/status/409' & \
ab -k -c 5 -n 5000 'http://localhost:8080/status/500' & \
ab -k -c 50 -n 5000 'http://localhost:8080/status/200?seconds_sleep=1' & \
ab -k -c 50 -n 2000 'http://localhost:8080/status/200?seconds_sleep=2'
```

## Пример дашборда
Находится в папке /grafana/example-dashboard.json