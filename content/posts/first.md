---
title: "Hugo. Установка и размещение на Github Pages."
date: 2023-04-01T02:09:10+07:00
draft: false
---

## Установка Hugo в Docker
Я буду использовать Docker, вы можете выбрать любой подходящий для вас способ на сайте [HUGO](https://gohugo.io/categories/installation/) 

Docker-compose.yaml

``` yaml
services:  
  hugo:
    image: klakegg/hugo:$HUGO_DOCKER_TAG
    container_name: hugo_srv
    # command: new site hugo_blog # запустить контейнер с этой командой для создания сайта
    # command: new post create-your-blog.md # запустить контейнер с этой командой для создания
    volumes:
      - "/srv/hugo_blog:/src"
    ports:
      - "1313:1313"
```

Или если вы установили HUGO локально

Создаем новый пост

```yaml
hugo new posts/info.md
```

Запускаем сервер локально, он будет доступен по адресу http://localhost:1313/

```
hugo server -D
```


Выбираем понравившуюся тему и копируем ее в папку /themes

В конфиг файле указываем название папки с темой

config.yaml

```yaml
baseURL: http://example.org/
languageCode: en-us
title: My New Hugo Site
theme: papermod
```
