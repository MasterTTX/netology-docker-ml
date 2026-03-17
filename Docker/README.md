# Docker homework

\# Домашняя работа к занятию "Docker и микросервисная архитектура"



\## Dockerfile



```dockerfile

FROM continuumio/miniconda3:latest



WORKDIR /app



COPY 1.sh /app/1.sh



RUN sed -i 's/\\r$//' /app/1.sh \&\& chmod +x /app/1.sh



RUN pip install mlflow boto3 pymysql



CMD \["/app/1.sh"]



Содержимое файла 1.sh



\#!/bin/bash

echo "Hello Netology"



Команда сборки



docker build -t netology-ml:netology-ml .



Лог сборки



\[+] Building 107.0s (11/11) FINISHED                                                               docker:desktop-linux

&#x20;=> \[internal] load build definition from Dockerfile                                                               0.0s

&#x20;=> => transferring dockerfile: 229B                                                                               0.0s

&#x20;=> \[internal] load metadata for docker.io/continuumio/miniconda3:latest                                           1.9s

&#x20;=> \[auth] continuumio/miniconda3:pull token for registry-1.docker.io                                              0.0s

&#x20;=> \[internal] load .dockerignore                                                                                  0.0s

&#x20;=> => transferring context: 2B                                                                                    0.0s

&#x20;=> \[1/5] FROM docker.io/continuumio/miniconda3:latest@sha256:b002473017c77d4b8bad6f8c49747e0298c37419a5ec69ca37e  0.0s

&#x20;=> => resolve docker.io/continuumio/miniconda3:latest@sha256:b002473017c77d4b8bad6f8c49747e0298c37419a5ec69ca37e  0.0s

&#x20;=> \[internal] load build context                                                                                  0.0s

&#x20;=> => transferring context: 25B                                                                                   0.0s

&#x20;=> CACHED \[2/5] WORKDIR /app                                                                                      0.0s

&#x20;=> CACHED \[3/5] COPY 1.sh /app/1.sh                                                                               0.0s

&#x20;=> \[4/5] RUN sed -i 's/\\r$//' /app/1.sh \&\& chmod +x /app/1.sh                                                     0.3s

&#x20;=> \[5/5] RUN pip install mlflow boto3 pymysql                                                                    68.1s

&#x20;=> exporting to image                                                                                            36.4s

&#x20;=> => exporting layers                                                                                           26.4s

&#x20;=> => exporting manifest sha256:c6ac96be5b4ed291e79998fd0a1e9d07ac9053cc331aeeb7cfd359e7a844c8d8                  0.0s

&#x20;=> => exporting config sha256:cdd51373e755062897cb7f45aee02e4eccb50247bc743093743af969e1b92d1c                    0.0s

&#x20;=> => exporting attestation manifest sha256:f68b177adb5398f2e2164ffdd07168777a10066b07cba97210770971b9ce0386      0.0s

&#x20;=> => exporting manifest list sha256:e444cf320ec241f9abcccf9d40780ea1de3e453229f9cd20c7aa6937b2f6f584             0.0s

&#x20;=> => naming to docker.io/library/netology-ml:netology-ml                                                         0.0s

&#x20;=> => unpacking to docker.io/library/netology-ml:netology-ml                                                      9.8s



Команда запуска контейнера



docker run --rm netology-ml:netology-ml



Результат запуска



Hello Netology

