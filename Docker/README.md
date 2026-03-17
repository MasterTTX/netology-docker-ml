# Домашняя работа к занятию "Docker и микросервисная архитектура"

## Dockerfile

```dockerfile
FROM continuumio/miniconda3:latest

WORKDIR /app

COPY 1.sh /app/1.sh

RUN sed -i 's/\r$//' /app/1.sh && chmod +x /app/1.sh

RUN pip install mlflow boto3 pymysql

CMD ["/app/1.sh"]
```

## Содержимое файла 1.sh

```bash
#!/bin/bash
echo "Hello Netology"
```

## Команда сборки

```bash
docker build -t netology-ml:netology-ml .
```

## Лог сборки

```md
## Лог сборки

```bash
[+] Building 107.0s (11/11) FINISHED
 => [5/5] RUN pip install mlflow boto3 pymysql
 => exporting to image
 => naming to docker.io/library/netology-ml:netology-ml

## Команда запуска контейнера

```bash
docker run --rm netology-ml:netology-ml
```

## Результат запуска

```bash
Hello Netology
```