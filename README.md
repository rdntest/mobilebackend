# task # 4
## 1. Создать репозиторий.
1.1 Создав репозиторий в Github аккаунте - клонировать его на локальную машину командой `git clone https://github.com/rdntest/mobilebackend.git` в общую папку.
1.2 Открыв Gitbash консоль в общей папке - проверить командой `ls -la` наличие появившегося репозитория.
1.3 Перейти в папку с клонированным репозиторием `cd mobilebackend`
## 2. Создать 3 любых коммита в ветке master
2.1 Создать 1 файл с расширением _'txt'_ `cat > 1.txt`
2.2 Проверить, что файл создался `ls -la`
2.3 Создать первый коммит
```SHELL
cat >> 1.txt
1
git add .
git commit -m 'the first commit'
```
2.4 Создать второй коммит
```SHELL
cat >> 1.txt
2
git add .
git commit -m 'the second commit'
```
2.5 Создать третий коммит
```SHELL
cat >> 1.txt
3
git add .
git commit -m 'the third commit'
```
2.6 Проверить, что все 3 коммита создались `git log`
## 3. Создать ветку branch_1 от ветки master.
3.1 Создать и переключиться на ветку branch_1 `git checkout -b branch_1`
3.2 Проверить, что находимся на нужной ветке `git branch`
## 4. Добавить в ветку branch_1 еще 1 коммит.
4.1 
```SHELL
cat >> 1.txt
4
git add .
git commit -m 'branch commit'
```
## 5. Выполнить слиятие ветки branch_1 в ветку master.
5.1 Переключиться на ветку master `git checkout main`  
5.2 Проверить коммиты `git log`. Последний должен быть _'the third commit'_  
5.3 Смержить новую ветку в мейн `git merge branch_1`  
5.4 Проверить, что добавлися новый коммит _'branch commit'_ `git log`  
5.5 Запушить изменения Main ветки `git push`  
5.6 Запушить изменения branch_1 ветки `git push origin branch_1`
## 6. Создать ветки branch_2 и branch_3 от ветки master.
6.1 Создание новых веток командой `git branch branch_2 & git branch branch_3`
6.2 Проверка, что ветки действительно создались `git branch`
6.3 Запушить все ветки на внешний репозиторий - `git push -u origin --all`, `-u` - _опция, которая позволяет отслеживать ссылку на удаленную ветку,_ `--all` - _данная опция позволяет запушить все ветки сразу._
## 7. В ветках branch_2 и branch_3 отменить коммит-слияние ветки branch_1 двумя различными способами.
7.1 Переключиться на ветку branch_2 `git checkout branch_2`  
7.2 Проверка последнего коммита _'branch commit'_ командой `git log`.  
7.3 Удаление последнего коммита командой `git reset --hard HEAD~1`  
7.8 Обновление на удаленном репозитории `git push --force`  
7.5 Переключиться на ветку branch_3 `git checkout branch_3`  
7.6 Проверка последнего коммита _'branch commit'_ командой `git log`. Скопировать ХЕШ коммита.  
7.7 Отмена последнего коммита по его ХЕШУ со всеми изменениями, путем создания нового - _'Rever "branch commit"_  `git revert -m 1 <hash>`  
7.8 Обновление на удаленном репозитории `git push --force`  

# BASH 

```SHELL
Unknown@DESKTOP-5M4DU36 MINGW64 ~/Desktop/Projects
$ git clone https://github.com/rdntest/mobilebackend.git
Cloning into 'mobilebackend'...
remote: Enumerating objects: 3, done.
remote: Counting objects: 100% (3/3), done.
remote: Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
Receiving objects: 100% (3/3), done.

Unknown@DESKTOP-5M4DU36 MINGW64 ~/Desktop/Projects
$ cd mobilebackend

Unknown@DESKTOP-5M4DU36 MINGW64 ~/Desktop/Projects/mobilebackend (main)
$ cat > 1.txt
1

Unknown@DESKTOP-5M4DU36 MINGW64 ~/Desktop/Projects/mobilebackend (main)
$ git add .
warning: in the working copy of '1.txt', LF will be replaced by CRLF the next time Git touches it

Unknown@DESKTOP-5M4DU36 MINGW64 ~/Desktop/Projects/mobilebackend (main)
$ git commit -m 'the first commit'
[main d618ac8] the first commit
 1 file changed, 1 insertion(+)
 create mode 100644 1.txt

Unknown@DESKTOP-5M4DU36 MINGW64 ~/Desktop/Projects/mobilebackend (main)
$ git log
commit d618ac87fbbc9e1cdd51e8edf3bde1aa11f37986 (HEAD -> main)
Author: Dmitry Romanushkov <d.romanushkov@gmail.com>
Date:   Sat Dec 9 20:59:59 2023 +0500

    the first commit

commit 5adb75008551435fb73855060280769b72303af4 (origin/main, origin/HEAD)
Author: Dmitry Romanushkov <121397031+rdntest@users.noreply.github.com>
Date:   Sat Dec 9 20:44:12 2023 +0500

    Initial commit

Unknown@DESKTOP-5M4DU36 MINGW64 ~/Desktop/Projects/mobilebackend (main)
$ cat >> 1.txt
2


Unknown@DESKTOP-5M4DU36 MINGW64 ~/Desktop/Projects/mobilebackend (main)
$ git add .
warning: in the working copy of '1.txt', LF will be replaced by CRLF the next time Git touches it

Unknown@DESKTOP-5M4DU36 MINGW64 ~/Desktop/Projects/mobilebackend (main)
$ git commit -m 'the second commit'
[main 9b038cd] the second commit
 1 file changed, 1 insertion(+)

Unknown@DESKTOP-5M4DU36 MINGW64 ~/Desktop/Projects/mobilebackend (main)
$ git log
commit 9b038cde4629ee33d80b3d5afca3ba261ff6101e (HEAD -> main)
Author: Dmitry Romanushkov <d.romanushkov@gmail.com>
Date:   Sat Dec 9 21:00:27 2023 +0500

    the second commit

commit d618ac87fbbc9e1cdd51e8edf3bde1aa11f37986
Author: Dmitry Romanushkov <d.romanushkov@gmail.com>
Date:   Sat Dec 9 20:59:59 2023 +0500

    the first commit

commit 5adb75008551435fb73855060280769b72303af4 (origin/main, origin/HEAD)
Author: Dmitry Romanushkov <121397031+rdntest@users.noreply.github.com>
Date:   Sat Dec 9 20:44:12 2023 +0500

    Initial commit

Unknown@DESKTOP-5M4DU36 MINGW64 ~/Desktop/Projects/mobilebackend (main)
$ cat >> 1.txt
3


Unknown@DESKTOP-5M4DU36 MINGW64 ~/Desktop/Projects/mobilebackend (main)
$ git add .
warning: in the working copy of '1.txt', LF will be replaced by CRLF the next time Git touches it

Unknown@DESKTOP-5M4DU36 MINGW64 ~/Desktop/Projects/mobilebackend (main)
$ git commit -m 'the third commit'
[main 57c4ead] the third commit
 1 file changed, 1 insertion(+)

Unknown@DESKTOP-5M4DU36 MINGW64 ~/Desktop/Projects/mobilebackend (main)
$ git log
commit 57c4eadede6c7c754c388e46bad0985d32d0ab9f (HEAD -> main)
Author: Dmitry Romanushkov <d.romanushkov@gmail.com>
Date:   Sat Dec 9 21:00:47 2023 +0500

    the third commit

commit 9b038cde4629ee33d80b3d5afca3ba261ff6101e
Author: Dmitry Romanushkov <d.romanushkov@gmail.com>
Date:   Sat Dec 9 21:00:27 2023 +0500

    the second commit

commit d618ac87fbbc9e1cdd51e8edf3bde1aa11f37986
Author: Dmitry Romanushkov <d.romanushkov@gmail.com>
Date:   Sat Dec 9 20:59:59 2023 +0500

    the first commit

commit 5adb75008551435fb73855060280769b72303af4 (origin/main, origin/HEAD)
Author: Dmitry Romanushkov <121397031+rdntest@users.noreply.github.com>
Date:   Sat Dec 9 20:44:12 2023 +0500

    Initial commit

Unknown@DESKTOP-5M4DU36 MINGW64 ~/Desktop/Projects/mobilebackend (main)
$ git checkout -b branch_1
Switched to a new branch 'branch_1'

Unknown@DESKTOP-5M4DU36 MINGW64 ~/Desktop/Projects/mobilebackend (branch_1)
$ cat >> 1.txt
4


Unknown@DESKTOP-5M4DU36 MINGW64 ~/Desktop/Projects/mobilebackend (branch_1)
$ git checkout main
Switched to branch 'main'
M       1.txt
Your branch is ahead of 'origin/main' by 3 commits.
  (use "git push" to publish your local commits)

Unknown@DESKTOP-5M4DU36 MINGW64 ~/Desktop/Projects/mobilebackend (main)
$ git checkout branch_1
Switched to branch 'branch_1'

Unknown@DESKTOP-5M4DU36 MINGW64 ~/Desktop/Projects/mobilebackend (branch_1)
$ cat >> 1.txt
4


Unknown@DESKTOP-5M4DU36 MINGW64 ~/Desktop/Projects/mobilebackend (branch_1)
$ git add .
warning: in the working copy of '1.txt', LF will be replaced by CRLF the next time Git touches it

Unknown@DESKTOP-5M4DU36 MINGW64 ~/Desktop/Projects/mobilebackend (branch_1)
$ git commit -m 'branch commit'
[branch_1 0a4badd] branch commit
 1 file changed, 1 insertion(+)

Unknown@DESKTOP-5M4DU36 MINGW64 ~/Desktop/Projects/mobilebackend (branch_1)
$ git checkout main
Switched to branch 'main'
Your branch is ahead of 'origin/main' by 3 commits.
  (use "git push" to publish your local commits)

Unknown@DESKTOP-5M4DU36 MINGW64 ~/Desktop/Projects/mobilebackend (main)
$ git log
commit 57c4eadede6c7c754c388e46bad0985d32d0ab9f (HEAD -> main)
Author: Dmitry Romanushkov <d.romanushkov@gmail.com>
Date:   Sat Dec 9 21:00:47 2023 +0500

    the third commit

commit 9b038cde4629ee33d80b3d5afca3ba261ff6101e
Author: Dmitry Romanushkov <d.romanushkov@gmail.com>
Date:   Sat Dec 9 21:00:27 2023 +0500

    the second commit

commit d618ac87fbbc9e1cdd51e8edf3bde1aa11f37986
Author: Dmitry Romanushkov <d.romanushkov@gmail.com>
Date:   Sat Dec 9 20:59:59 2023 +0500

    the first commit

commit 5adb75008551435fb73855060280769b72303af4 (origin/main, origin/HEAD)
Author: Dmitry Romanushkov <121397031+rdntest@users.noreply.github.com>
Date:   Sat Dec 9 20:44:12 2023 +0500

    Initial commit

Unknown@DESKTOP-5M4DU36 MINGW64 ~/Desktop/Projects/mobilebackend (main)
$ cat 1.txt
1
2
3

Unknown@DESKTOP-5M4DU36 MINGW64 ~/Desktop/Projects/mobilebackend (main)
$ git merge branch_1
Updating 57c4ead..0a4badd
Fast-forward
 1.txt | 1 +
 1 file changed, 1 insertion(+)

Unknown@DESKTOP-5M4DU36 MINGW64 ~/Desktop/Projects/mobilebackend (main)
$ git push
Enumerating objects: 13, done.
Counting objects: 100% (13/13), done.
Delta compression using up to 12 threads
Compressing objects: 100% (8/8), done.
Writing objects: 100% (12/12), 1.03 KiB | 1.03 MiB/s, done.
Total 12 (delta 0), reused 0 (delta 0), pack-reused 0
To https://github.com/rdntest/mobilebackend.git
   5adb750..0a4badd  main -> main

Unknown@DESKTOP-5M4DU36 MINGW64 ~/Desktop/Projects/mobilebackend (main)
$ git push origin branch_1
Total 0 (delta 0), reused 0 (delta 0), pack-reused 0
remote:
remote: Create a pull request for 'branch_1' on GitHub by visiting:
remote:      https://github.com/rdntest/mobilebackend/pull/new/branch_1
remote:
To https://github.com/rdntest/mobilebackend.git
 * [new branch]      branch_1 -> branch_1

Unknown@DESKTOP-5M4DU36 MINGW64 ~/Desktop/Projects/mobilebackend (main)
$ git branch branch_2 & git branch branch_3
[1] 2990
[1]+  Done                    git branch branch_2

Unknown@DESKTOP-5M4DU36 MINGW64 ~/Desktop/Projects/mobilebackend (main)
$ git branch
  branch_1
  branch_2
  branch_3
* main

Unknown@DESKTOP-5M4DU36 MINGW64 ~/Desktop/Projects/mobilebackend (main)
$ git checkout branch_2
Switched to branch 'branch_2'

Unknown@DESKTOP-5M4DU36 MINGW64 ~/Desktop/Projects/mobilebackend (branch_2)
$ git log --oneline
0a4badd (HEAD -> branch_2, origin/main, origin/branch_1, origin/HEAD, main, branch_3, branch_1) branch commit
57c4ead the third commit
9b038cd the second commit
d618ac8 the first commit
5adb750 Initial commit

Unknown@DESKTOP-5M4DU36 MINGW64 ~/Desktop/Projects/mobilebackend (branch_2)
$ git push -u origin --all
Total 0 (delta 0), reused 0 (delta 0), pack-reused 0
To https://github.com/rdntest/mobilebackend.git
 * [new branch]      branch_2 -> branch_2
 * [new branch]      branch_3 -> branch_3
branch 'branch_1' set up to track 'origin/branch_1'.
branch 'main' set up to track 'origin/main'.
branch 'branch_2' set up to track 'origin/branch_2'.
branch 'branch_3' set up to track 'origin/branch_3'.

Unknown@DESKTOP-5M4DU36 MINGW64 ~/Desktop/Projects/mobilebackend (branch_2)
$ git reset --hard HEAD~1
HEAD is now at 57c4ead the third commit

Unknown@DESKTOP-5M4DU36 MINGW64 ~/Desktop/Projects/mobilebackend (branch_2)
Revert "branch commit"

[branch_3 6d1bb19] Revert "branch commit"
 1 file changed, 1 deletion(-)

Unknown@DESKTOP-5M4DU36 MINGW64 ~/Desktop/Projects/mobilebackend (branch_3)
$ git log
commit 6d1bb191c0ba25cc7cd9850c079d4cb4d9558f79 (HEAD -> branch_3)
Author: Dmitry Romanushkov <d.romanushkov@gmail.com>
Date:   Sat Dec 9 21:06:59 2023 +0500

    Revert "branch commit"

    This reverts commit 0a4badd2c9014de4b093bb104cb941029c12a491.

commit 0a4badd2c9014de4b093bb104cb941029c12a491 (origin/main, origin/branch_3, origin/branch_1, origin/HEAD, main, branch_1)
Author: Dmitry Romanushkov <d.romanushkov@gmail.com>
Date:   Sat Dec 9 21:02:15 2023 +0500

    branch commit

commit 57c4eadede6c7c754c388e46bad0985d32d0ab9f (origin/branch_2, branch_2)
Author: Dmitry Romanushkov <d.romanushkov@gmail.com>
Date:   Sat Dec 9 21:00:47 2023 +0500

    the third commit

commit 9b038cde4629ee33d80b3d5afca3ba261ff6101e
Author: Dmitry Romanushkov <d.romanushkov@gmail.com>
Date:   Sat Dec 9 21:00:27 2023 +0500

    the second commit

commit d618ac87fbbc9e1cdd51e8edf3bde1aa11f37986
Author: Dmitry Romanushkov <d.romanushkov@gmail.com>
Date:   Sat Dec 9 20:59:59 2023 +0500

    the first commit

commit 5adb75008551435fb73855060280769b72303af4
Author: Dmitry Romanushkov <121397031+rdntest@users.noreply.github.com>
Date:   Sat Dec 9 20:44:12 2023 +0500

    Initial commit

Unknown@DESKTOP-5M4DU36 MINGW64 ~/Desktop/Projects/mobilebackend (branch_3)
$ git push --force
Enumerating objects: 5, done.
Counting objects: 100% (5/5), done.
Delta compression using up to 12 threads
Compressing objects: 100% (2/2), done.
Writing objects: 100% (3/3), 312 bytes | 312.00 KiB/s, done.
Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
To https://github.com/rdntest/mobilebackend.git
   0a4badd..6d1bb19  branch_3 -> branch_3
```
