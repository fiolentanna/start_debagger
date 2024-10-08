# git pull vs git fetch

## $ git fetch

Данная команда связывается с указанным удалённым проектом и забирает все те данные проекта, которых у вас ещё нет. После того как вы выполнили команду, у вас должны появиться ссылки на все ветки из этого удалённого проекта, которые вы можете просмотреть или слить в любой момент.

**Важно отметить**, что команда git fetch забирает данные в ваш локальный репозиторий, но не сливает их с какими-либо вашими наработками и не модифицирует то, над чем вы работаете в данный момент. Вам необходимо вручную слить эти данные с вашими, когда вы будете готовы.
При использовании git fetch исключены конфликты. 

## $ git pull

Команда git pull работает как комбинация команд git fetch и git merge, т. е. Git вначале забирает изменения из указанного удалённого репозитория, а затем пытается слить их с текущей веткой.

При использовании git pull возможны конфликты, которые нужно будет потом решать, используя git merge или  git rebase.


## $ git commit --amend

Крайне часто разработчики делают коммит и сразу понимают, что забыли добавить часть файлов через git add. Оставшуюся часть изменений можно дослать следующим коммитом.

Есть еще один способ. Если изменения еще не были отправлены во внешнюю систему, можно добавить изменения в текущий коммит. Для этого во время коммита добавляется флаг **--amend**
Например:
Забыли добавить README.md
1. Добавили файл
   git add README.md
3. Выполнили git commit --amend
   После этой команды откроется редактор, ожидающий ввода описания коммита. Здесь можно поменять сообщение или выйти из редактора, оставив старое. 

В реальности --amend не добавляет изменения в существующий коммит. Этот флаг приводит к откату коммита через git reset и выполнению нового коммита с новыми данными. Поэтому мы и видим ровно один коммит, хотя команда git commit выполнялась два раза (первый раз — когда сделали ошибочный коммит).

Чтобы не открывался редактор для ввода описания коммита к команде git commit --amend можно добавить опцию --no-edit. В этом случае описание коммита не изменится. 


