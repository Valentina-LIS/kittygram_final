#  Проект Kittygram

Проект Kittygram представляет собой социальную сеть, с помощью которой пользователи после прохождения аутентификации и авторизации могут публиковать фотографии своих питомцев, выбирать их цвет, указывать их имена и достижения, редактировать и удалять свои публикации, а также просматривать контент других пользователей.
В проекте реализованы настройка запуска Kittygram в контейнерах, автоматическое тестирование и деплой проекта на удалённый сервер.
Имеется зона администратора для редактирования всех обьектов в базе данных.
<details>
  <summary>Нажмите, чтобы развернуть</summary>
  <img src="https://github.com/Valentina-LIS/kittygram_final/blob/main/Китиграмм.JPG" alt="Изображение">
</details>
![Главная](https://github.com/Valentina-LIS/kittygram_final/blob/main/Китиграмм.JPG)
![Создать пост](https://github.com/Valentina-LIS/kittygram_final/blob/main/Киттиграм.JPG)

## Запуск проекта

Для начала необходимо клонировать репозиторий:
```
git@github.com:Valentina-LIS/kittygram_final.git
```
В развернутом проекте в корневой папке есть пример файла .env (.env.example) - создайте свой, либо переименуйте уже существующий
В корневой директории выполните команду для запуска контейнеров docker
```
docker compose up --build
```
После разворачивания проекта в контейнерах необходимо применить миграции и скопировать статику:
```
docker compose -f docker-compose.production.yml exec backend python manage.py migrate
docker compose -f docker-compose.production.yml exec backend python manage.py collectstatic
docker compose -f docker-compose.production.yml exec backend cp -r /app/collected_static/. /backend_static/static/
```
После разворачивания проект локально доступен по адресу:
```
http://127.0.0.1:9000/
```

## Стек использованных технологий

+ Python 3.9
+ Django 3.2.16
+ Django REST framework 3.12.4
+ Nginx 1.22.1
+ Node.js 13.12.0
+ Docker 25.0.3

## Адрес сайта:

https://kittygram.bounceme.net/

### Авторы проекта

Проект создан и предоставлен командой **Яндекс Практикум** для использования в рамках учебной программы **Яндекс Практикум** курс "Python-разработчик".
Автор создания инфраструктуры проекта: Лисина Валентина (teleghram - @lisinaval, GitHub - Valentina-LIS)

2024 г
