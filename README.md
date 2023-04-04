# Git
Создаём папку проекта
```bash
mkdir folder && cd folder
```
Инициализируем Git в папке проекта
```bash
git init
```
Вы на ветке `master` по умолчанию в Git и `main` в Github
-
Затянуть проект в папку с Github
```bash
git clone "https://github.com/Bentax/git"
```
После каждого изменения в файле сохраняем `Ctrl+S`
При настроенной IDE изменения сразу попадают на удалённый сервер
Для того, чтобы изменения проиндексировать:
```bash
git add .
```
Закоммитим изменения
```bash
git commit -m "Comment"
```
