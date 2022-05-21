В данной лабораторноый работе я рассмотрю создание сервера для разработки веб-приложений с помощью Vagrant.
=================

Для начала требуется установить Vagrant и VirtualBox и выполнить настройку.

Работать будем в командной строке Windows. Запускаем ее. Проверяем корректность установки Vagrant, прописывая команду.
`Vagrant`
<img width="599" alt="image" src="https://user-images.githubusercontent.com/99497212/169657656-ce9bcb59-7a5c-45a2-a11c-34944c7da433.png">

Далее нужно создать папку .homestead в домашней библиотеке пользователя "C:\Users\"Имя пользователя"" (данный путь далее заменяю ~/) и добавить в эту папку файлы из скриншота ниже (файлы есть в репозитории).

<img width="576" alt="image" src="https://user-images.githubusercontent.com/99497212/169658768-91041667-fa21-416b-96b6-15c0502df58d.png">

Для доступа к машине потребуются SSH-ключи. Для этого можно использовать программу Putty. (https://www.chiark.greenend.org.uk/~sgtatham/putty/latest.html) Генерируем приватный и публичный ключи и сохраняем их в папку ~/.ssh.

<img width="442" alt="image" src="https://user-images.githubusercontent.com/99497212/169658791-be1c3c65-bd41-4107-8eb1-f8eeaa7a2062.png">

<img width="573" alt="image" src="https://user-images.githubusercontent.com/99497212/169658801-e53d6698-93b0-4270-8810-27eb75d3e1bb.png">


**Запуск виртуального сервера**
---------------

В командной строке выбираем папку ~/.homestead 

`cd .homestead`

Далее запускаем виртуальную машину.

`vagrant up`

<img width="611" alt="image" src="https://user-images.githubusercontent.com/99497212/169658882-ab8d6ee1-4c02-4583-bbe2-3605ad55dd62.png">


Начнется загрузка VirtualBox-образа от разработчиков Laravel.
Спустя несколько минут виртуальная машина полностью настроится и установит все необходимые компоненты и параметры.

<img width="933" alt="image" src="https://user-images.githubusercontent.com/99497212/169658914-a340d99b-558b-4ecf-91e6-20ed5cbce22a.png">

**Подключение к серверу**
--------------

С помощью программы PuTTy подключаемся к серверу.
Вводим данные как на скриншотах ниже. Нужно так же указать адрес к приватному ключу, которыый лежит в папке ~/.ssh

<img width="332" alt="image" src="https://user-images.githubusercontent.com/99497212/169659201-bc5347ee-1bbd-4cb4-b412-d0f18f5e8292.png">

<img width="334" alt="image" src="https://user-images.githubusercontent.com/99497212/169659215-006828f5-2308-4473-9ee9-3e2e326ab01e.png">

После успешного запуска сервера создаем папку ~/code и вводим команды.
```
cd code
composer create-project laravel/laravel Laravel --prefer-dist
```
<img width="480" alt="image" src="https://user-images.githubusercontent.com/99497212/169659345-69d4284d-99f4-44fa-9ed1-bd85add74333.png">

После успешной загрузки открываем папку ~/code и видим папку Laravel, значит мы все сделали правильно.
Осталось сделать самую малость, нужно открыть файл hosts в режиме администратора (у меня данный файл находится тут C:\Windows\System32\drivers\etc) и добавляем строку 192.168.56.56 homestead.test

Теперь открываем в браузере адрес  homestead.test и видим результат нашей работы.

<img width="960" alt="image" src="https://user-images.githubusercontent.com/99497212/169659487-7e138180-05a1-4231-b4b9-4ce2b9c092c8.png">

