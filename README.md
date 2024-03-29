# hw03_forms 
расширение проекта hw02_community https://github.com/DumaDim/hw02_community.git
## Описание проекта
1. Создано и подключено приложение core:
    - размещён и зарегистрирован фильтр addclass, позволяющий добавлять CSS-класс к тегу шаблона;
    - создан и зарегистрирован контекст-процессор, добавляющий текущий год на все страницы в переменную {{ year }}.

2. Создано и подключено приложение about:
    - созданы статические страницы /about/author/ и /about/tech/;
    - ссылки на эти страницы добавлены в навигацию сайта.

3. Подключено приложение django.contrib.auth, его urls.py подключен к головному urls.py.
4. Создано и подключено приложение users:
    - переопределены шаблоны для адреса /auth/login/ (авторизация);
    - переопределены шаблоны для адреса /auth/logout/ (выход из аккаунта);
    - создана страница /auth/signup/ с формой для регистрации пользователей.    

5. В приложении posts сделано следующее:
    - создана страница пользователя profile/<username>/. На ней отображаются посты пользователя;
    - создана отдельная страница поста posts/<post_id>/;
    - подключен паджинатор, он выводит по десять постов (на главную страницу, на страницу профайла, на страницу группы)

6. Создана навигация по разделам.

7. Добавлена в шапку сайта ссылка «Новая запись», она видна только авторизованным пользователям и ведёт на страницу /create/.

8. На странице /create/ создана форма для добавления новой публикации:
    - view-функция для страницы /create/ называется post_create();
    - name для path() страницы /create/ - post_create;
    - в контекст шаблона страницы /create/ передается переменная form. Она содержит объект PostForm, в котором два поля:
       - text (обязательное для заполнения поле);
       - group (необязательное для заполнения);
    - после валидации формы и создания нового поста автор перенаправляется на страницу своего профайла /profile//.
9. Добавлена страница редактирования записи с адресом /posts/<post_id>/edit/. View-функцию для этой страницы post_edit().
    - Права на редактирование только у автора этого поста. Остальные пользователи перенаправляются на страницу просмотра поста.
    - При генерации страницы в контекст передается переменная form, в ней два поля: text и group.
    - Для страницы редактирования поста применяется тот же HTML-шаблон, что и для страницы создания нового поста: posts/create_post.html.
10. Шаблон немного усложнен:
    - при редактировании поста заголовок «Добавить запись» заменяется на «Редактировать запись»;
    - надпись на кнопке отправки формы зависит от операции: «Добавить» для новой записи и «Сохранить» — для редактирования.
 
## Технологии
Python 3.7, Django 2.2, Pytest

## Установка проекта из репозитория
### Шаг 1
Клонировать репозиторий себе на компьютер
```bash
https://github.com/DumaDim/hw03_forms.git
```

### Шаг 2
Создать и активировать виртуальное окружение
```bash
python -m venv venv
source venv/Scripts/activate
```

### Шаг 3
Установить зависимости из файла requirements.txt
```bash
pip install -r requirements.txt
```

