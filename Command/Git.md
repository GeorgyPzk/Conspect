Запуск GIT
1. Git.clone в VC  (cntrl+shift+p вызов строки)
2. Вставляешь ссылку в репозиторий + лог
3. File->workspace  работаешь через в VC workspace


# GIT

`git add .| git commit -m '' | git push`

Тут будет игнорировать все кроме указанной папке

`git add ./*какая то папка*| git commit -m '' | git push`

Копирование удаленного репозитория в папку где сейчас находимся

`git clone <url>`

Соединяет локальный репозиторий и удаленный

`git remote add <name> <url>`

Загружает обратно удаленные файлы с репозитория(удаленного)

`git restore`

Создат новую ветку, но не переходит в нее

`git branch <breanchName>`

Запулит, созданную в локальном репозитории ветку, в удаленном репозитории (разобрать что значит orgin, не очень ясно)!

`git push --set-upstream origin <breanchName>`

Удаляет ветку

`git branch -d <breanchName>`

Переходит в новую ветку

`git checkout <breanchName>`

Отмена изменений в файле?? (заменит версией из последнего коммита)

`git checkout -- FileName`

Проверка конфигурации(там есть email и ник, использующейся в данный момент)

`git config --list`

Добавляет конкретный коммит(возможно из другой ветки) в нынешнюю ветку

`git cherry-pick <commitNum>`

Откат к конкретному коммит(нужно писать каждый коммит который хочешь откатить)

`git revert d225d0812a5f1f7fc600b10144a11d08ac1b47bc`

Обновление репозиторя

`git pull`
`git featch - укороченный git pull ( git featch + git merge = git pull )`