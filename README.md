<фрагмент_вставки_значка>
┌──(emoterrorist㉿emo)-[~]
└─$ export GITHUB_USERNAME=emoterrorist

┌──(emoterrorist㉿emo)-[~]
└─$ export GITHUB_EMAIL=sergey.plotnikov2006@mail.ru

┌──(emoterrorist㉿emo)-[~]
└─$ export GITHUB_TOKEN=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

┌──(emoterrorist㉿emo)-[~]
└─$ alias edit=nano

┌──(emoterrorist㉿emo)-[~]
└─$ cd ${GITHUB_USERNAME}/workspace

┌──(emoterrorist㉿emo)-[~/emoterrorist/workspace]
└─$ source scripts/activate

┌──(emoterrorist㉿emo)-[~/emoterrorist/workspace]
└─$ mkdir ~/.config
mkdir: невозможно создать каталог «/home/emoterrorist/.config»: Файл существует

┌──(emoterrorist㉿emo)-[~/emoterrorist/workspace]
└─$ cat > ~/.config/hub <<EOF
> github.com:
> - user: ${GITHUB_USERNAME}
>   oauth_token: ${GITHUB_TOKEN}
>   protocol: https
> EOF

┌──(emoterrorist㉿emo)-[~/emoterrorist/workspace]
└─$ git config --global hub.protocol https

┌──(emoterrorist㉿emo)-[~/emoterrorist/workspace]
└─$ mkdir projects/lab02 && cd projects/lab02
mkdir: невозможно создать каталог «projects/lab02»: Файл существует

┌──(emoterrorist㉿emo)-[~/emoterrorist/workspace]
└─$ cd projects/lab02

┌──(emoterrorist㉿emo)-[~/emoterrorist/workspace/projects/lab02]
└─$ git init
hint: Using 'master' as the name for the initial branch. This default branch name
hint: is subject to change. To configure the initial branch name to use in all
hint: of your new repositories, which will suppress this warning, call:
hint:
hint: 	git config --global init.defaultBranch <name>
hint:
hint: Names commonly chosen instead of 'master' are 'main', 'trunk' and
hint: 'development'. The just-created branch can be renamed via this command:
hint:
hint: 	git branch -m <name>
Инициализирован пустой репозиторий Git в /home/emoterrorist/emoterrorist/workspace/projects/lab02/.git/

┌──(emoterrorist㉿emo)-[~/emoterrorist/workspace/projects/lab02]
└─$ git config --global user.name ${GITHUB_USERNAME}

┌──(emoterrorist㉿emo)-[~/emoterrorist/workspace/projects/lab02]
└─$ git config --global user.email ${GITHUB_EMAIL}

┌──(emoterrorist㉿emo)-[~/emoterrorist/workspace/projects/lab02]
└─$ git config -e --global

┌──(emoterrorist㉿emo)-[~/emoterrorist/workspace/projects/lab02]
└─$ git remote add origin https://github.com/${GITHUB_USERNAME}/lab02.git

┌──(emoterrorist㉿emo)-[~/emoterrorist/workspace/projects/lab02]
└─$ git pull origin master
fatal: couldn't find remote ref master

┌──(emoterrorist㉿emo)-[~/emoterrorist/workspace/projects/lab02]
└─$ git pull origin main
remote: Enumerating objects: 3, done.
remote: Counting objects: 100% (3/3), done.
remote: Compressing objects: 100% (2/2), done.
remote: Total 3 (delta 0), reused 0 (delta 0), pack-reused 0 (from 0)
Распаковка объектов: 100% (3/3), 1.45 КиБ | 1.45 МиБ/с, готово.
Из https://github.com/emoterrorist/lab02
 * branch            main       -> FETCH_HEAD
 * [новая ветка]     main       -> origin/main

┌──(emoterrorist㉿emo)-[~/emoterrorist/workspace/projects/lab02]
└─$ touch README.md

┌──(emoterrorist㉿emo)-[~/emoterrorist/workspace/projects/lab02]
└─$ git status
Текущая ветка: master
Неотслеживаемые файлы:
  (используйте «git add <файл>...», чтобы добавить в то, что будет включено в коммит)
	README.md

индекс пуст, но есть неотслеживаемые файлы
(используйте «git add», чтобы проиндексировать их)

┌──(emoterrorist㉿emo)-[~/emoterrorist/workspace/projects/lab02]
└─$ git add README.md

┌──(emoterrorist㉿emo)-[~/emoterrorist/workspace/projects/lab02]
└─$ git commit -m"added README.md"
[master 793a1c0] added README.md
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 README.md

┌──(emoterrorist㉿emo)-[~/emoterrorist/workspace/projects/lab02]
└─$ git push origin master
Username for 'https://github.com': emoterrorist
Password for 'https://emoterrorist@github.com': 
Перечисление объектов: 4, готово.
Подсчет объектов: 100% (4/4), готово.
При сжатии изменений используется до 12 потоков
Сжатие объектов: 100% (2/2), готово.
Запись объектов: 100% (3/3), 290 байтов | 290.00 КиБ/с, готово.
Total 3 (delta 0), reused 0 (delta 0), pack-reused 0 (from 0)
remote: 
remote: Create a pull request for 'master' on GitHub by visiting:
remote:      https://github.com/emoterrorist/lab02/pull/new/master
remote: 
To https://github.com/emoterrorist/lab02.git
 * [new branch]      master -> master

┌──(emoterrorist㉿emo)-[~/emoterrorist/workspace/projects/lab02]
└─$ git pull origin master
remote: Enumerating objects: 4, done.
remote: Counting objects: 100% (4/4), done.
remote: Compressing objects: 100% (2/2), done.
remote: Total 3 (delta 0), reused 0 (delta 0), pack-reused 0 (from 0)
Распаковка объектов: 100% (3/3), 993 байта | 993.00 КиБ/с, готово.
Из https://github.com/emoterrorist/lab02
 * branch            master     -> FETCH_HEAD
   793a1c0..95971de  master     -> origin/master
Обновление 793a1c0..95971de
Fast-forward
 .gitignore | 4 ++++
 1 file changed, 4 insertions(+)
 create mode 100644 .gitignore

┌──(emoterrorist㉿emo)-[~/emoterrorist/workspace/projects/lab02]
└─$ git log
commit 95971de7877042bd3456c44e3a91576d4c783924 (HEAD -> master, origin/master)
Author: emo_terrorist <sergey.plotnikov2006@mail.ru>
Date:   Mon Apr 14 15:45:16 2025 +0300

    Create .gitignore

commit 793a1c075d5f3efec14971207ef7b1b15671df4e
Author: emoterrorist <sergey.plotnikov2006@mail.ru>
Date:   Mon Apr 14 15:44:12 2025 +0300

    added README.md

commit 14a0596c8c4afa518ec4d1147520f200b39f0bc9 (origin/main)
Author: emo_terrorist <sergey.plotnikov2006@mail.ru>
Date:   Mon Apr 14 15:36:58 2025 +0300

    Initial commit

┌──(emoterrorist㉿emo)-[~/emoterrorist/workspace/projects/lab02]
└─$ mkdir sources

┌──(emoterrorist㉿emo)-[~/emoterrorist/workspace/projects/lab02]
└─$ mkdir include

┌──(emoterrorist㉿emo)-[~/emoterrorist/workspace/projects/lab02]
└─$ mkdir examples

┌──(emoterrorist㉿emo)-[~/emoterrorist/workspace/projects/lab02]
└─$ cat > sources/print.cpp <<EOF
> #include <print.hpp>
> void print(const std::string& text, std::ostream& out)
> {
> out<<text;
> }
> void print(const std::string& text, std::ofstream& out)
> {
> out<<text;
> }
> EOF

┌──(emoterrorist㉿emo)-[~/emoterrorist/workspace/projects/lab02]
└─$ cat > include/print.hpp <<EOF
> #include <fstream>
> #include <iostream>
> #include <string>
> void print(const std::string& text, std::ofstream& out);
> void print(const std::string& text, std::ostream& out = std::cout);
> EOF

┌──(emoterrorist㉿emo)-[~/emoterrorist/workspace/projects/lab02]
└─$ cat > examples/example1.cpp <<EOF
> #include <print.hpp>
> int main(int argc, char** argv)
> {
> print("hello");
> }
> EOF

┌──(emoterrorist㉿emo)-[~/emoterrorist/workspace/projects/lab02]
└─$ cat > examples/example2.cpp <<EOF
> #include <print.hpp>
> #include <fstream>
> int main(int argc, char** argv)
> {
>   std::ofstream file("log.txt");
>   print(std::string("hello"), file);
> }
> EOF
