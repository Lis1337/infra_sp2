# api_yamdb
Проект YaMDb собирает отзывы (Review) пользователей на произведения (Title). Произведения делятся на категории: «Книги», «Фильмы», «Музыка». 

###Запуск приложения

1. Загрузить проект с github; загрузить контейнеры с помощью docker командой:
```
docker pull lis1337/infra_sp2:latest
```
2. Зайти в папку проекта создать виртуальное окружение и установить необходимое программное обеспечение:
```
virtualenv -p python3 venv
source venv/bin/activate
pip install -r requirements.txt
```
3. Соберите проект с помощью:
```
docker-compose up
```
4. Выполните необходимые миграции и проведите тесты с помощью:
```
docker exec -it <container_id> bash
python manage.py migrate
pytest
```
5. При необходимости заполнить базу данных находясь внутри контейнера выполните:
```
python manage.py runscript import_csv
```
6. Для создания суперпользователя необходимо войти в контейнер и воспользоваться командой:
```
python manage.py createsuperuser
```

##Version
latest


##Author
lis1337


##License
no license
