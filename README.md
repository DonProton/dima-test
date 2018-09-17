# Начальный курс веб-разработки

* Студент:  `undefined`.
* Ментор: `undefined`.
* План занятий: [нате](https://drive.google.com/open?id=1JoOGNCRK-BmZIJtLw8_5IDlTgl8UgIfLi1NBEPe-Qyo).
* Требования к выпускному проекту: [тут](https://drive.google.com/open?id=1NsSIElGCQ6BvFFpnPRSQdisfcBkq-W0WqcLrTM7wl2I).
* Основные репозитории: [здесь](https://github.com/Maximumstart-initial-course).
* Репозиторий с домашними заданиями: [там](https://github.com/MaximumStart/initial-course).

---

Не удаляй и ничего не меняй в файлах: `.gitignore`, `package.json`, `package-lock.json`.

Если есть необходимость размещать какие-то свои личные файлы, то в корню локального репозитория есть специальная папка `Personal`, которая не индексируется и не прилетает на проверку.

---

# Что делать, если git был только недавно установлен или переустанавливался?

## 1. Зарегистрируйся

Если у тебя еще нет аккаунта, то зарегистрируйся на [github.com](https://github.com/join).

## 2. Создай SSH-ключ, если еще этого не делал

Для этого в `Git BASH` или в терминале запусти команду:

```bash
ssh-keygen
```

Нажимай `Enter` до появления графического ключа.

После чего, в домашней папке (для того, чтобы узнать расположение домашней папки, в `Git BASH` введи символ `~` и нажми `Enter`) найди папку `.ssh`, а в ней файл `id_rsa.pub`. Открой его в любом текстовом редакторе и полностью скопируй его содержимое.

Зайди на GitHub -> Settings -> SSH and GPG keys -> New SSH key. В поле __Title__ введи любое название, а в поле __Key__ вставь содержимое файла `id_rsa.pub`.

## 3. Представься

Укажи свой логин на Github и email, которые потом будут записываться в каждый коммит. Делается это с помощью команд:

```bash
git config --global user.email "you@example.com"
git config --global user.name "Your Name"
```

# Что делать, если у меня есть аккаунт на GitHub и Git уже настроен? 

## 1. Найди свой основной репозиторий и форкни его

На [странице курса](https://github.com/Maximumstart-initial-course) найди свой основной репозиторий, перейди в него и нажми кнопку `Fork`. Все дальнейшее обучение будет проходить непосредственно в форкнутом репозитории.

## 2. Клонируй репозиторий себе на компьютер

Найди форкнутый репозиторий у себя в аккаунте, нажми в нем на кнопку `Clone or download`, выбери `Use SSH` и скопируй ссылку. На рабочем столе или в любой другой папке откройте `Git BASH` и введи следующую команду:

```bash
git clone <ссылка_из_гитхаба>
```
## 3. Измени файл README.md

В этом курсе мы будем создавать папки, которые будут называться так же, как и в репозитории с домашками (first-lesson, second-lesson) и работать в них. Сегодня ты еще только учишься работать с Git, поэтому ограничимся изменением файла `README.md`. В этом файле пока еще нет информации о тебе, вместо нее ты видишь надписи `undefined`. Заполни эту информацию, чтобы нам было удобнее работать с тобой. Все остальное оставь без изменений.

## 4. Установи линтер

Установи [Node.js](https://nodejs.org/), после чего открой папку и запусти из нее Git BASH:

Установи все необходимые для работы файлы командой: 

```bash
npm i
```

## 5. Поправь .gitignore

Открой файл `.gitignore` в корне проекта и в первых двух строках убери знак октоторпа "#". После этого на GitHub не будут отправляться папки __Personal__ и сам файл __.gitignore__.

## 6. Отправь все файлы в свой форк на Гитхаб

Для этого в своей рабочей папке запусти `Git BASH` и выполни команду

```bash
git add .
```

чтобы проиндексировать файл. После чего выполни:

```bash
git commit -m 'Изменил Readme'
```

Консоль подскажет что-то вида:

```
[master c75f147] Изменил Readme
 1 file changed, 26 insertions(+), 1 deletion(-)
 rewrite README.md (100%)
```

Отправь свой коммит на Гитхаб командой:

```bash
git push origin master
```

В дальнейшем можно будет использовать короткую форму `git push`, не указывая адрес репозитория и ветку.

## 7. Создай pull request

Убедитесь, что в репозитории появился свежий коммит и нажмите на кнопку `New pull request`, на появившейся странице нажмите `Create pull request`, оставьте комментарий для наставника и сообщите о готовом к проверке домашнем задании в Телеграм. В течение нескольких часов задание проверят и сольют с главным репозиторием.

## 8. Сообщи ментору

После создания pull request'a, сообщи ментору о том, что задание готово к проверке.

# Критерии оценивания

1. В конце курса студенты проходят компьютерное тестирование, которое включает все вопросы курса -- Git, HTML5, CSS3. Минимальный проходной балл -- 60%.

2. Все домашние задания должны быть выполнены, если домашние задания не выполнялись, то __студент не получает макет__.

3. Если студент набирает минимальные 60%, он получает .psd-файл выпускного проекта и список требований к нему. На сдачу готового проекта выделяется 14 дней, все даты и требования будут объявлены заранее.

# Как синхронизировать основной и локальный репозитории?

1. Добавляем адрес основного репозитория, если еще этого не сделали:

```bash
git remote add main <адрес основого репозитория>
```

2. Получаем ветки из основного репозитория:

```bash
git fetch main
```

3. Сливаем наш основной репозиторий с локальным:

```bash
git merge main/master
```

# Как тестировать мой код?

Мы задали определенные правила, исполнение которых и проверяет линтер в автоматическом режиме. Роль ментора при этом не теряется, однако, если код не проходит проверку линтером, то и ментор его не примет.

Если не знаешь значения какой-то ошибки, то просто загугли. Все эти правила хорошо задокументированы.

Для прохождения теста введи команду:

```bash
npm test или npm t
```

Некоторые ошибки линтер предложит исправить автоматически. Для этого запусти команду:

```bash
npm run all:fix
```