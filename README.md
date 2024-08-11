# Компоненты проекта:
- npm 8.19.4
- PHP 8.3.0 (cli) (built: Jun  8 2023 15:27:12) (NTS)
- Composer version 2.7.1 2022-12-22 15:33:54
- Laravel Framework 10.48.4

# План по разворачиванию проекта:
1. Сделать клонирование проекта `git clone https://github.com/AnnaBruzgalova/diplom-cinema.git`
2. Открыть проект в IDE
3. Выполнить в терминале команду для установки зависимостей `npm install`
4. Выполнить в терминале команду для установки зависимостей `composer install`
5. Создать файла окружения .env из .env.example и сделать настройки БД (DB_CONNECTION=sqlite, DB_DATABASE=database\database.sqlite) 
6. Cоздать файл базы данных database\database.sqlite
7. Выполнить в терминале команду для генерации APP_KEY в env-файле `php artisan key:generate`
8. Выполнить в терминале команду для применения миграций (создания таблиц БД) `php artisan migrate` 
9. Выполнить в терминале команду для наполнителей `php artisan db:seed`
10. Выполнить в терминале команду для запуска локального сервера `php artisan serve`
11. Открыть браузер с адресом `http://127.0.0.1:8000/` и войти в административную часть с логином `demo@demo.ru` и паролем `123` для заполнения данных о залах и сеансах
12. Открыть браузер с адресом `http://127.0.0.1:8000/` и войти в клиентскую как гость для выбора сеанса фильма и покупки билета
    
# Описание таблиц базы данных sqlite:
## Залы - halls
- name - наименование зала
- rows - количество рядов
- cols - количество мест в ряду
- price - цена за обычное место
- price_vip - цена за vip место
- is_open - зал открыт для продаж
## Фильмы - movies
- title - наименование фильма
- duration - продолжительность фильма
## Сеансы - sessions
- start - начало сеанса
- hall_id - id зала
- movie_id - id фильма
- selected_seats - занятые/купленные места зала в виде сериализованной json-строки
- seance-seats - все места зала для сеанса в виде сериализованной json-строки
## Места - seats
- hall_id - id зала
- type_seat - вид места (обычное st-standart, vip, отсутствует- disable)
