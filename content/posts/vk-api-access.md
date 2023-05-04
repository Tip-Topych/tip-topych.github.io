---
title: "Vk Api Access"
date: 2023-04-29T22:24:42+07:00
draft: false
---


### 1. Для взаимодействия с VK API создаем **Standalone-приложение** и сохраняем **“id приложения“, “Защищённый ключ“, “Сервисный ключ доступа“**
![vk_app_settings](/vk_app_settings_2023_04_28.png)

### 2. Включаем Open Api и указываем адрес нашего сайта, пока не принципиально рабочий или нет.

### 3. Теперь нужно получить ключ авторизации для приложения и настроить права. с параметром scope=offline полученный токен не будет иметь время жизни и менять его придется в с лучае смены пароля аккаунта и т.п. 

```
https://oauth.vk.com/authorize?client_id=ID_ПРИЛОЖЕНИЯ&display=page
&redirect_uri=https://api.vk.com/blank.html&scope=offline,wall,photos
&response_type=code
```

### 4. Получаем access_token. Отправляем запрос по новому URL  `client_id`, `client_secret` и полученный выше код

```
https://oauth.vk.com/access_token?client_id=ID_ПРИЛОЖЕНИЯ
&client_secret=ЗАЩИЩЕННЫЙ_КЛЮЧ&redirect_uri=https://api.vk.com/blank.html
&code=СЕКРЕТНЫЙ_КОД
```

В ответе получаем `access_token`

Готово, вы великолепны!
Теперь можно приступать к написанию ботов или еще чего-нибудь интересного.
