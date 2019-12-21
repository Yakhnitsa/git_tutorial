

#Шпаргалка с основными командами для Git
(ссылка на команды)(https://agladky.ru/blog/git-cheat-sheet/)

## КОНФИГУРАЦИЯ
	git config --global user.name "[name]" — установить имя, которое будет прикрепляться к коммиту.

	git config --global user.email "[email address]" — установить email, который будет прикрепляться к коммиту.

	git config --global color.ui auto — включить полезную подсветку командной строки.

	git config --global push.default current — обновлять удаленную ветку с таким же именем, что и локальная, при пуше изменений (если не указано иного).

	git config --global core.editor [editor] — установить редактор для редактирования сообщений коммита.

	git config --global diff.tool [tool] — установить программу для разрешения конфликтов при слиянии.
	
	Создание псевдонимов:

	git config --global alias.ch checkout - псевдоним для команды checkout -> ch команда выглядит как git ch

	git config --global alias.cmt commit - псевдоним для commit -> git cmt

	git config --global alias.st status - эквивалент git status -> git st

	git config --global alias.unstage 'reset HEAD --' - псевдоним для отката изменений git unstage [filename] -> git reset HEAD -- [filenme]

	git config --global alias.last 'log -1 HEAD' - просмотр последнего коммита

	git config --global alias.getgraph 'log --pretty=format:"%Cgreen%h%Creset %cd %C(blue)%an %C(yellow)%s" --graph --date=format:"%Y-%m-%d %H:%M"' построение дерева коммитов по формату
	
## СОЗДАНИЕ РЕПОЗИТОРИЕВ
	git init [project-name] — создать новый локальный репозиторий с заданным именем.

	git clone [url] — загрузить проект и его полную историю изменений.
	
## ОТСЛЕЖИВАНИЕ ИЗМЕНЕНИЙ
	
	git status — полный список изменений файлов, ожидающих коммита.

	git status -s — краткий вид изменений.

	git diff — показать изменения в файлах, которые еще не были добавлены в индекс коммита (staged).

	git add [file] — сделать указанный файл готовым для коммита.

	git add . — сделать все измененные файлы готовыми для коммита.

	git add '*.txt' — добавить только файлы, соответствующие указанному выражению.

	git add --patch filename — позволяет выбрать какие изменения из файла добавятся в коммит.

	git diff --staged — показать что было добавленно в индекс с помощью git add, но еще не было закоммиченно.

	git diff HEAD — показать что изменилось с последнего коммита.

	git diff HEAD^ — показать что изменилось с предпоследнего коммита.

	git diff [branch] — сравнить текущую ветку с заданной.

	git difftool -d — то же самое, что и diff, но показывает изменения в заданной difftool.

	git difftool -d master.. — показать изменения, сделанные в текущей ветке.

	git diff --stat — показать статистику какие файлы были изменены и как.

	git reset [file] — убрать файлы из индекса коммита (изменения не теряются).

	git commit — записать изменения в репозиторий. для написания сообщения откроется назначенный редактор.

	git commit -m "[descriptive message]" — записать изменения с заданным сообщением.

	git commit --amend — добавить изменения к последнему коммиту.
	
## РАБОТА С ВЕТКАМИ

	git branch — список всех локальных веток в текущей директории.

	git branch [branch-name] — создать новую ветку.

	git checkout [branch-name] — переключиться на указанную ветку и обновить рабочую директорию.

	git checkout -b <name> <remote>/<branch> — переключиться на удаленную ветку.

	git cheсkout [filename] — вернуть файл в первоначальное состояние если он еще не был добавлен в индекс коммита.

	git merge [branch] — соединить изменения в текущей ветке с изменениями из заданной.

	git merge --no-ff [branch] — соединить ветки без режима “fast forwarding”.

	git branch -a — посмотреть полный список локальных и удаленных веток.

	git branch -d [branch] — удалить заданную ветку.

	git branch -D [branch] — принудительно удалить заданную ветку, игнорируя ошибки.

	git branch -m <oldname> <newname> — переименовать ветку.	