# [Репозиторий](https://github.com/oxiteam/rabota08)

![check-code](https://github.com/oxiteam/rabota08/workflows/check-code/badge.svg)
![client-build](https://github.com/oxiteam/rabota08/workflows/client-build/badge.svg)
![dashboard-build](https://github.com/oxiteam/rabota08/workflows/dashboard-build/badge.svg)
![test-deploy](https://github.com/oxiteam/rabota08/workflows/test-deploy/badge.svg)

### Основные ресурсы
* https://rabota08.ru - сайт
* https://dashboard.rabota08.ru - админка
* https://t.me/rabota08ru - телеграм
* https://www.instagram.com/rabota08.ru - инстаграм
* https://vk.com/rabota08ru - Вконтакте
* https://t.me/helprabota08 - Админ в телеграм
* Телефон сервиса - 8(937)464-60-02

### Ресурсы для тестирования доработок:
* https://test.rabota08.ru - тестовый сайт
* https://test.dashboard.rabota08.ru - тестовая админка
* https://t.me/rabota08_test - тестовый телеграм
* https://vk.com/public200589946 - тестовый Вконтакте

### Прямые конкуренты
* https://hh.ru - headhunter
* https://www.avito.ru/ - Авито
* https://vkrabota.ru - ВКработа
* https://minsoc08.ru/ - Центр занятости населения
* https://vk.com/work_08 - Работа08
* https://vk.com/vacancy08 - Вакансии

### Прочее
* [Мониторинг ошибок - Sentry APM](https://sentry.io/organizations/oxitech/issues/)
* [Мониторинг работы сайта и фоновых задач - Cron monitoring](https://cronitor.io/app)

## Стек технологий
OS: **Ubuntu 20.04**

### Frontend
  * [**TypeScript**](http://typescript-lang.ru/docs/Basic%20Types.html)
  * [**React.js**](https://ru.reactjs.org/)
    * Обязательно разобраться как использовать [хуки](https://ru.reactjs.org/docs/hooks-intro.html)
  * **CSS**
    * [Flexbox](https://tproger.ru/translations/how-css-flexbox-works/)
    * [CSS Modules](https://frontender.info/css-modules-part-1-need/)
    * В будущем возможно будет использоваться CSS-фреймворк [Bootstrap](https://getbootstrap.com/) через библиотеку [react-bootstrap](https://react-bootstrap.github.io/)
  * Роутинг - **React router** (устарел, будет заменен **Next.js**)
### Backend
  * [**Node.js**](https://learn.javascript.ru/screencast/nodejs) (>=14.15.1)
  * База данных - [**MongoDB**](https://metanit.com/nosql/mongodb/) (через библиотеку [**Mongoose**](https://runebook.dev/ru/docs/mongoose/guide), возможно в будущем будет заменен на **PostgreSQL**)
  * Фреймворк **Express.js** (устарел, будет заменен **Next.js**)
  * Фоновые задачи - [Agenda](https://github.com/agenda/agenda)

## Что почитать
* **JavaScript. Подробное руководство**
  * [Купить](https://www.labirint.ru/books/779734/)
  * [Скачать](https://vk.com/wall-51126445_77418)
* **React. Современные шаблоны для разработки приложений**
  * [Купить, 1600р](https://www.labirint.ru/books/822856/)
  * [Скачать](https://dokumen.pub/react-2-9785446114924-9781492051725.html)
* **Профессиональный TypeScript. Разработка масштабируемых JavaScript-приложений**
  * [Купить, 1300р](https://www.ozon.ru/product/professionalnyy-typescript-razrabotka-masshtabiruemyh-javascript-prilozheniy-chernyy-boris-202138569/?sh=mHPxLtZR)
  * [Скачать](https://vk.com/wall-79831840_47370)
* **Грокаем алгоритмы**
    * [Купить, 800p](https://www.ozon.ru/product/grokaem-algoritmy-illyustrirovannoe-posobie-dlya-programmistov-i-lyubopytstvuyushchih-139296295/)
    * [Скачать](https://vk.com/wall-54530371_184116)

## Дизайн
* [Макеты сайта](https://www.figma.com/file/jhoQzBKXvzZj7ozfH5NQzU/%D0%BC%D0%BE%D0%B9-%D0%BC%D0%B0%D0%BA%D0%B5%D1%82?node-id=0%3A1)
* [Библиотека компонентов для админки](https://www.figma.com/community/file/831698976089873405)
* [Библиотека компонентов для клиента](https://www.figma.com/community/file/876022745968684318)
* Шрифт на клиенте - **PT Sans**

## Развертывание проекта
### Установка зависимостей
* Установить Ubuntu через подсистему Windows для Linux (**WSL**)
  * ```$ wsl --install``` в командной строке от имени администратора
* (опционально) Скачать редактор кода [WebStorm](https://www.jetbrains.com/toolbox-app/) 
* Запустить консоль **WSL** (В пуске будет новое приложение "Ubuntu")
* Придумать ник (маленькими буквами на англ) и записать пароль
* Клонировать репозиторий в файловую систему WSL

* Запустить скрипт установки, ответить на его вопросы

  ```shell
    $ sudo apt-get update -y && sudo apt-get install -y curl git ansible
    $ curl -fsSL https://cli.github.com/packages/githubcli-archive-keyring.gpg | dd of=/usr/share/keyrings/githubcli-archive-keyring.gpg
    $ echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/githubcli-archive-keyring.gpg] https://cli.github.com/packages stable main" | tee /etc/apt/sources.list.d/github-cli.list > /dev/null
    $ sudo apt-get update -y && sudo apt-get install -y gh

    $ git config --global core.autocrlf false

    $ gh auth login

    # Настроить SSH для доступа к GitHub - https://docs.github.com/en/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent)
    $ ssh-keygen -t ed25519 -C "ВАШ ЕМЕЙЛ"
    $ eval "$(ssh-agent -s)"
    $ ssh-add ~/.ssh/id_ed25519
    $ gh ssh-key add ~/.ssh/id_ed25519.pub
    
    # Клонировать репозиторий в файловую систему WSL
    $ git clone git@github.com:oxiteam/rabota08.git ~ -b develop
    
    # Установить зависимости проекта
    
    $ ansible-playbook -K ./rabota08/ansible/local-deploy.yaml
   ```

* Добавить файлы `.env` в `server`, `client`, `dashboard` (взять из телеграм беседы)

### Разработка
* Запустить проект

  `$ make run`
* Открыть `localhost:3000` в браузере 🎉
* Отписаться об успехе! Если что-то пошло не так, написать о проблеме с приложенными скриншотами

## Дополнительно

* Зарегистрироваться в [ZenHub](https://app.zenhub.com/workspaces/rabota08-61914f80e0714b001c4910de/board?invite=true) и установить их [расширение](https://www.zenhub.com/extension) для трекинга задач
* (опционально) Установить консоль [Cmder](https://cmder.net/) для удобного доступа к **WSL**
* (опционально) Настроить **WebStorm** для максимального удобства
  * [Скачать и установить шрифт Fira Code](https://github.com/tonsky/FiraCode/releases/download/6.2/Fira_Code_v6.2.zip)
    * Включить его в **File | Settings | Editor | Color Scheme | Color Scheme Font**
  * Установить plugin [Material UI](https://plugins.jetbrains.com/plugin/8006-material-theme-ui)
  * Отключить неиспользуемые плагины
    * Vagrant
    * Live Edit
    * Refactor-X
    * XPathView + XSLT
    * Angular and AngularJS
    * CoffeeScript
    * Cordova
    * Cucumber.js
    * Karma
    * Meteor
    * Polymer & Web Components
    * Vue.js
    * Gherkin
    * Less
    * Stylus
    * Tailwind CSS
    * EJS
    * Haml
    * Handlebars/Mustache
    * Windows 10 Light Theme
    * Mercurial
    * Subversion
    * Code With Me
    * IDE Features Trainer
    * TextMate Bundles
    * Time Tracking
  * **Git**

     Пример - http://screenshot.ru/d317350ee956458ba3de9cee2748764b.png
  * **Node.js**

    Пример - http://screenshot.ru/f7df22bb62fd26323b1db00a3553eb37.png
  * **TypeScript**
    
    Пример - http://screenshot.ru/e9a6f42381ca409d9fb0ede17e07f32d.png
  * **Eslint**
    
    Пример - http://screenshot.ru/66f32a071da72f3926b713b0e881b204.png
  * **Prettier**

     Пример - http://screenshot.ru/26728225ad02771672f32732177c8553.png
* Если WebStorm глючит
  Открыть `Help / Edit VM Options` и изменить
  ```
   -Xms256m
   -Xmx2048m
  ```
* Если виртуальная машина съедает слишком много памяти:
  * Создать файл `.wslconfig` в папке юзера Windows:
    ```
    [wsl2]
      memory=6GB
    ```
  * Перезапустить виртуальную машину
* Если при попытке залогиниться падает ошибка, то нужно зайти на https://whatismyipaddress.com/ и прислать мне свой IP, чтобы я мог добавить его в список разрешенных.
