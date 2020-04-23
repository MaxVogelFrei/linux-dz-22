# Простая защита от DDOS

## Задание
Написать конфигурацию nginx, которая даёт доступ клиенту только с определенной cookie.
Если у клиента её нет, нужно выполнить редирект на location, в котором кука будет добавлена, после чего клиент будет обратно отправлен (редирект) на запрашиваемый ресурс.

Смысл: умные боты попадаются редко, тупые боты по редиректам с куками два раза не пойдут

Для выполнения ДЗ понадобятся
* https://nginx.org/ru/docs/http/ngx_http_rewrite_module.html
* https://nginx.org/ru/docs/http/ngx_http_headers_module.html

## Решение

Образ в docker hub - maxvogelfrei/dz22:latest

проверка
```bash
docker run -d -p 80:80 maxvogelfrei/dz22:latest
```
```bash
[root@centos7 linux-dz-22]# curl http://localhost/otus.txt
<html>
<head><title>302 Found</title></head>
<body>
<center><h1>302 Found</h1></center>
<hr><center>nginx/1.17.10</center>
</body>
</html>
```
В браузере:
![dz22.png](dz22.png)


