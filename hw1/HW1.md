# HW1. Развертывание своей системы визуализации

## Задание:

Закрепить материалы практикума повторением всех
действий из методички или записи вебинара:

- 📌Прислать реквизиты доступа развернутой системы
  визуализации с актуальными и валидными данными.
- 📌Если нет возможности настроить выход системы в интернет,
  можно пристать скриншоты с локального доступа.
- Описать сложности, с которыми столкнулись при
  развертывании

---

1. Выполнена установка и настройка ОС Debian 11

https://cdimage.debian.org/debian-cd/current/amd64/iso-cd/debian-12.8.0-amd64-netinst.iso

![hw1_img1](./img/isoDebian.jpg)

Просмотр дискового пространства занимаемого ВМ

![hw1_img2](./img/htopDebian.jpg)

---

2. Выполнена установка и базовая настройка MQTT брокера Mosquitto:

использовал следующий ресурс:
http://ftp.ru.debian.org/debian/pool/main/o/openssl/libssl1.1_1.1.1w-0+deb11u1_amd64.deb

![hw1_img2.1](./img/mqtt1.jpg)

![hw1_img2.2](./img/mqtt2.jpg)

![hw1_img2.3](./img/mqtt3.jpg)

![hw1_img2.4](./img/mqtt4.jpg)

![hw1_img2.5](./img/mqtt5.jpg)

На этом этапе MQTT брокер Mosquitto у нас успешно запущен и защищён паролем.

---

3. Установка Node-RED + Node.js:

Nodesource: <https://deb.nodesource.com/>

![hw2_image3.1](./img/NodeRed1.jpg)

![hw2_image3.2](./img/NodeRed2.jpg)

![hw2_image3.3](./img/NodeRed3.jpg)

![hw2_image3.4](./img/NodeRed4.jpg)

Проверка функционирования: <http://192.168.113.129:1880/>

![hw2_image3.5](./img/NodeRed5.jpg)

---

4. Установка и настройка WireGuard:

![hw2_image4.1](./img/WG1.jpg)

![hw2_image4.2](./img/WG2.jpg)

![hw2_image4.3](./img/WG3.jpg)

![hw2_image4.4](./img/WG4.jpg)

---

5. Установка InfluxDB2 + Telegraf + Grafana:

Grafanasource: <https://mirrors.huaweicloud.com/grafana/10.2.0/>

![hw2_image5.1](./img/influxdb5.1.jpg)

![hw2_image5.2](./img/influxdb5.2.jpg)

![hw2_image5.3](./img/influxdb5.3.jpg)

![hw2_image5.4](./img/influxdb5.4.jpg)

![hw2_image5.5](./img/influxdb5.5.jpg)

![hw2_image5.6](./img/influxdb5.6.jpg)

![hw2_image5.7](./img/influxdb5.7.jpg)

Проверим, что InfluxDB и Grafana доступны, зайдя по адресам:
http://192.168.113.129:8086/ и http://192.168.113.129:3000/

![hw2_image5.8](./img/influxdb5.8.jpg)

![hw2_image5.9](./img/Graf5.1.jpg)

6. Проверим ресурсы системы после настройки:

![hw2_image6](./img/htop2.jpg)

6.1 Проверим работу связки mqtt-брокер – telegraf – influxdb – Grafana:

![hw2_image6.1](./img/topik.jpg)

![hw2_image6.2](./img/topik2.jpg)

![hw2_image6.3](./img/topik3.jpg)

![hw2_image6.4](./img/topik4.jpg)

На этом настройка первого дашборда по визуализации условной температуры завершена.

6.2 Альтернатива с Node-RED

![hw2_image6.2.1](./img/NodeRed_flow.jpg)

![hw2_image6.2.2](./img/NodeRed_flow2.jpg)

![hw2_image6.2.3](./img/NodeRed_flow3.jpg)

![hw2_image6.2.4](./img/NodeRed_flow4.jpg)

7. Проверка доступности всех компонентов системы извне (через интернет):

настройка проброса портов на модеме:

![hw2_image7](./img/huawei.jpg)

настройка нашего доменного имени:

![hw2_image7.1](./img/no-ip.jpg)

![hw2_image7.2](./img/huawei_ddns1.jpg)

![hw2_image7.3](./img/no_page.jpg)

доступ к приложениям через интернет, при указании
публичного IP адреса и порта приложения - неудался. По итогу работы с iptables - также не решило проблему.
