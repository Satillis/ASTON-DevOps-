# Выполнение ДЗ 3

## 1. Создание файла
- Открыть терминал и создать файл:
```bash
nano script.sh
```
- Написать код
```bash
#!/bin/bash

mkdir -p /opt/app
touch /opt/app/log.txt

while true
do
    RANDOM_STRING=$(tr -dc 'a-zA-Z0-9' </dev/urandom | head -c $((RANDOM % 20 + 1)))
    echo "$RANDOM_STRING" >> /opt/app/log.txt
    sleep 17
done
```
- Сохраните файл:
    Ctrl + O
    Enter
    Vtrl + X

## 2. Сделать скрипт исполняемым
```bash
chmod +x script.sh
```

## 3. Запуск
```bash
sudo ./script.sh
```
## 4. Проверка
Просмотр содержимого файла:
```bash
cat /opt/app/log.txt
```
Просмотр в реальном времени:
```bash
tail -f /opt/app/log.txt
```