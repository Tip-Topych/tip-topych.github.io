---
layout: post
title:  "Установка ESPHome + dashboard в Docker"
date:   2021-05-06 21:31:20 +0700
categories: smarthome esphome
---

# Установка ESPHome + dashboard в Docker


![https://telegra.ph/file/f8256a357241e24c58ad3.png](https://telegra.ph/file/f8256a357241e24c58ad3.png)

Качаем образ

```docker
docker pull esphome/esphome

```

Запускаем контейнер с dashboard на порту 6052

```docker
docker run --rm -v "${PWD}":/config --net=host -it esphome/esphome

```

Бонус. Если ESPHome и устройства находятся в разных подсетях, и в Dashboard все время отображаются некрасиво красными, нужно добавить в переменные

```docker
ESPHOME_DASHBOARD_USE_PING=true

```

![https://telegra.ph/file/5a2448a38257f2edde647.png](https://telegra.ph/file/5a2448a38257f2edde647.png)

![https://telegra.ph/file/766bba10edebcf53988d3.png](https://telegra.ph/file/766bba10edebcf53988d3.png)

![https://telegra.ph/file/809fc0bb11a329fdc8b02.png](https://telegra.ph/file/809fc0bb11a329fdc8b02.png)