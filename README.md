![Crowdfunding](https://i.ibb.co/k6pj0Qt/htum-6.png)
# Git tutorial
- Создаём папку проекта и переходим в неё
```bash
mkdir folder && cd folder
```
- Инициализируем Git в папке проекта
```bash
git init
```
Вы на ветке `master` по умолчанию в Git или `main` в Github
- Затянуть проект в папку с Github
```bash
git clone "https://github.com/Bentax/git"
```
После каждого изменения в файле сохраняем `Ctrl+S`
При настроенной IDE изменения сразу попадают на `remote server`
- Для того, чтобы все изменения проиндексировать и закоммитить с комментарием:
```bash
git add .
git commit -m "Comment"
```
Перемещение файлов
```bash
mkdir lib
git mv hello.html lib
```
Отменить проиндексированные изменения
```bash
git reset HEAD <file>
```
Отменить коммит без захода в редактор `--no-edit`
```bash
git revert HEAD --no-edit
```
Сбросить коммиты до `<hash>`
```bash
git reset --hard <hash>
```
Настроим алиасы для удобства работы
```bash
git config --global alias.co checkout
git config --global alias.ci commit
git config --global alias.st status
git config --global alias.br branch
git config --global alias.hist "log --pretty=format:'%h %ad | %s%d [%an]' --graph --date=short"
git config --global alias.type 'cat-file -t'
git config --global alias.dump 'cat-file -p'
```
Работа с тегами
```bash
git tag v1
git co v1^
git tag
v1
v1-beta
git tag -d v1
git hist master --all
```
Создать ветку
```bash
git co -b <branch>
```
Слить ветки (возможный конфликт решается редактированием файла)
```bash
git co <branch>
git merge master
```
Либо можно сбросить ветки до последнего коммита перед слиянием и сделать rebase
```bash
git co <branch>
git reset --hard <hash>
git co master
git reset --hard <hash>
git co <branch>
git rebase master
git co master
git merge <branch>
```
Теперь ветки branch и master идентичны
Извлечение изменений из удалённого репозитория
```bash
git fetch
```
Коммиты из удалённого репозитория видны в локальном:
```bash
git hist --all
* 01b623f 2023-04-04 | Update README.md (origin/main, origin/HEAD) [Andrey Kuzin]
* f7c2e1c 2023-04-04 | Update README.md [Andrey Kuzin]
* 9033eb7 2023-04-04 | Update README.md (HEAD -> main) [Andrey Kuzin]
* 859c681 2023-04-04 | Update README.md [Andrey Kuzin]
* f5871ca 2023-04-04 | Create README.md [Andrey Kuzin]
```
Слить извлеченные изменения в локальную ветку master
```bash
git merge origin/main
```
- Объединение fetch & merge в одну команду
```bash
git pull
```
- Отправить изменения в `remote repo`
```bash
git push
```
