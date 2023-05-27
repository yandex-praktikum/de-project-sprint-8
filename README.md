# Проект 8-го спринта

### Описание
Репозиторий предназначен для сдачи проекта 8-го спринта.

### Как работать с репозиторием
1. В вашем GitHub-аккаунте автоматически создастся репозиторий `de-project-sprint-8` после того, как вы привяжете свой GitHub-аккаунт на Платформе.
2. Скопируйте репозиторий на свой компьютер. В качестве пароля укажите ваш `Access Token`, который нужно получить на странице [Personal Access Tokens](https://github.com/settings/tokens)):
	* `git clone https://github.com/{{ username }}/de-project-sprint-8.git`
3. Перейдите в директорию с проектом: 
	* `cd de-project-sprint-8`
4. Выполните проект и сохраните получившийся код в локальном репозитории:
	* `git add .`
	* `git commit -m 'my best commit'`
5. Обновите репозиторий в вашем GitHub-аккаунте:
	* `git push origin main`

### Структура репозитория
Вложенные файлы в репозиторий будут использоваться для проверки и предоставления обратной связи по проекту. Поэтому постарайтесь публиковать ваше решение согласно установленной структуре — так будет проще соотнести задания с решениями.

Внутри `src` расположены две папки:
- `/src/dags`;
- `/src/sql`.

#1 Действиме 1 - Подготовить инфраструктуру в telegram боте запросить Модуль 8: Потоковая обработка данных (проект)
#1.1 Открыть visual studio и поменять HostName


###Подготовка инфраструктуры и выполлнение действий для начала работы скрипта
#Шаг 1. Проверить работу потока.

#1.1 Открыть visual studio и поменять HostName
#1.2 Запустить виртуальную машину по данному хосту
#1.3 Установить докер и запустить Attach Shell
#2 Создать в директории  /data/ txt-файл first_message который мы будем отправлять в брокер
#2.1 Проверить, есть ли директория /data внутри контейнера: 
#cd / (выйти в корень), 
#ls -la (проверить содержимое)
#2.2 Перейти в папку /data (cd /data) и создать текстовый файл (touch first_message.txt) 
#2.3 Перейти в текстовый редактор (vi first_message.txt) 
#2.4 Открыть режим редактирования (e) 
#2.5 Вставить скопированные строки, не выходя из режима INSERT (через shift) 
#first_message:{"restaurant_id": "123e4567-e89b-12d3-a456-426614174000","adv_campaign_id": "123e4567-e89b-12d3-a456-426614174003","adv_campaign_content": "first campaign","adv_campaign_owner": "Ivanov Ivan Ivanovich","adv_campaign_owner_contact": "iiivanov@restaurant.ru","adv_campaign_datetime_start": 1659203516,"adv_campaign_datetime_end": 2659207116,"datetime_created": 1659131516} 
#2.6 Режи ввода команд shift + ":" - обязательно на буквах, не цифрах
#2.6.1 Выйти из режима INSERT (ESC) и сохранить изменения (:wq)
#2.7 Залить данные в свой топик
#kafkacat -b rc1b-2erh7b35n4j4v869.mdb.yandexcloud.net:9091 -X security.protocol=SASL_SSL -X sasl.mechanisms=SCRAM-SHA-512 -X sasl.username="de-student" -X sasl.password="ltcneltyn" -X ssl.ca.location=/usr/local/share/ca-certificates/Yandex/YandexCA.crt -t antongrigo -K: -P -l /data/first_message.txt
#2.7 Вызвать привычный jupyter notebook --allow-root (Порядок имеет значение)


##№Postgresql, таблица, данные##

#1 - создать или запустить postgresql в docker "sprint8_project"
#docker run --name sprint8_project -p 5432:5432 -e POSTGRES_USER=jovyan -e POSTGRES_PASSWORD=jovyan -d postgres:13.3
#2 - Создать таблицу в базе public 
#CREATE TABLE public.subscribers_restaurants (id serial4 NOT NULL, client_id varchar NOT NULL, restaurant_id varchar NOT NULL, CONSTRAINT pk_id PRIMARY KEY (id));
#INSERT INTO public.subscribers_restaurants(client_id, restaurant_id) VALUES ('223e4567-e89b-12d3-a456-426614174000', '123e4567-e89b-12d3-a456-426614174000');
#INSERT INTO public.subscribers_restaurants(client_id, restaurant_id) VALUES ('323e4567-e89b-12d3-a456-426614174000', '123e4567-e89b-12d3-a456-426614174000');
#INSERT INTO public.subscribers_restaurants(client_id, restaurant_id) VALUES ('423e4567-e89b-12d3-a456-426614174000', '123e4567-e89b-12d3-a456-426614174000');
#INSERT INTO public.subscribers_restaurants(client_id, restaurant_id) VALUES ('523e4567-e89b-12d3-a456-426614174000', '123e4567-e89b-12d3-a456-426614174000');
#INSERT INTO public.subscribers_restaurants(client_id, restaurant_id) VALUES ('623e4567-e89b-12d3-a456-426614174000', '123e4567-e89b-12d3-a456-426614174000');
#INSERT INTO public.subscribers_restaurants(client_id, restaurant_id) VALUES ('723e4567-e89b-12d3-a456-426614174000', '123e4567-e89b-12d3-a456-426614174000');
#INSERT INTO public.subscribers_restaurants(client_id, restaurant_id) VALUES ('823e4567-e89b-12d3-a456-426614174000', '123e4567-e89b-12d3-a456-426614174000');
#INSERT INTO public.subscribers_restaurants(client_id, restaurant_id) VALUES ('923e4567-e89b-12d3-a456-426614174000', '123e4567-e89b-12d3-a456-426614174001');
#INSERT INTO public.subscribers_restaurants(client_id, restaurant_id) VALUES ('923e4567-e89b-12d3-a456-426614174000', '123e4567-e89b-12d3-a456-426614174001');
#INSERT INTO public.subscribers_restaurants(client_id, restaurant_id) VALUES ('023e4567-e89b-12d3-a456-426614174000', '123e4567-e89b-12d3-a456-426614174000');
#SELECT * FROM public.subscribers_restaurants


