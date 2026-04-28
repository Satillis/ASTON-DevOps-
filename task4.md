# Задание 4

## Создание локальной доменной записи app.local
Открой файл:
```bash
sudo nano /etc/hosts
```

Добавить строку:

```
127.0.0.1 app.local
```
Сохранить и закрыть

## Bash скрипт (Сохранён как check_url.sh)
```bash
#!/bin/bash

URL=$1

# Проверка: передан ли аргумент
if [ -z "$URL" ]; then
  echo "Enter URL"
  exit 1
fi

# Проверка доступности
curl --silent --fail --max-time 5 "$URL" > /dev/null

if [ $? -ne 0 ]; then
  echo "Resource is NOT reachable: $URL"
  exit 1
else
  echo "Resource is reachable: $URL"
  exit 0
fi
```

Пример использования
```bash
./check_url.sh http://app.local