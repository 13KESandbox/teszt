# Git parancssori kezelése

Miután telepítve van a git for windows (A VS valószínűleg megtette. Ellenőrizhető a konzolon kiadott git --version paranccsal )

1. A parancssorban betallózzuk a kívánt könyvtárat

2. git init - Ezzel létrejön egy rejtett könyvár .git néven
C:\git>git init
Initialized empty Git repository in C:/git/.git/

3. git status - 
C:\git>git status
On branch master

No commits yet

Untracked files:
  (use "git add <file>..." to include in what will be committed)

        teszt.txt - ezt hoztam létre, hogy ne legyen üres a könyvtár(pirossal írja)

nothing added to commit but untracked files present (use "git add" to track)

4. git add teszt.txt - hozzáadjuk a helyi staging area-hoz (sok fájl esetén egyszerűen *, vagy *.txt, stb.)

5. git status -
git status
On branch master

No commits yet

Changes to be committed:
  (use "git rm --cached <file>..." to unstage) - ezzel le lehet venni és visszaáll a 4. pont előtti állapot

        new file:   teszt.txt - a git add hozzáadta a staging területhez  (zölddel íródik ki)
        
 6. git commit -m "Első verzió hozzáadva a repohoz" -
 git commit -m "Első verzió hozzáadva a repohoz"
[master (root-commit) 6f27f87] Első verzió hozzáadva a repohoz
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 teszt.txt
 A helyi repositoryba került a stage területen levő fájl
 
 7. git status -
 git status
On branch master
nothing to commit, working tree clean - minden OK!

#####################################################################################################
#Eddig a saját gépen kezeltük a gitet, most ezt hozzákapcsoljuk a távoli szerverhez pl. a Githubhoz.#
#####################################################################################################

8. Az accountod alatt hozz létre egy új repositoryt, másold vágólapra a linkjét!

9. git remote add origin <link> - 
C:\git>git remote add origin https://github.com/13KESandbox/teszt.git

10. git push -u origin master - Ez másolja a távoli repoba a helyit.
Ha hibaüzenetet kapunk:C:\git>git push -u origin master
To https://github.com/13KESandbox/teszt.git
 ! [rejected]        master -> master (fetch first)
error: failed to push some refs to 'https://github.com/13KESandbox/teszt.git'
hint: Updates were rejected because the remote contains work that you do
hint: not have locally. This is usually caused by another repository pushing
hint: to the same ref. You may want to first integrate the remote changes
hint: (e.g., 'git pull ...') before pushing again.
hint: See the 'Note about fast-forwards' in 'git push --help' for details. 

Tegyünk a leírtak szerint:

git pull origin master -

Újabb hibaüzenet: 

C:\git>git pull origin master
warning: no common commits
remote: Counting objects: 23, done.
remote: Compressing objects: 100% (16/16), done.
remote: Total 23 (delta 5), reused 5 (delta 0), pack-reused 0
Unpacking objects: 100% (23/23), done.
From https://github.com/13KESandbox/teszt
 * branch            master     -> FETCH_HEAD
 * [new branch]      master     -> origin/master
fatal: refusing to merge unrelated histories

Rövid anyázás után Stackoverlow és itt a megoldás:

git pull origin master --allow-unrelated-histories

A hiba oka: a távoli repo létrehozásakor ha bejelölted a README létrehozását, ott lesz egy
README.md fájl, ami nincs a helyi repoban. Azt a fenti paranccsal lehet lehúzni.

Ha minden jó, ilyesminek kell megjelenni:

C:\git>git pull origin master --allow-unrelated-histories
From https://github.com/13KESandbox/teszt
 * branch            master     -> FETCH_HEAD
Merge made by the 'recursive' strategy.
 README.md | 64 +++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++
 1 file changed, 64 insertions(+)
 create mode 100644 README.md

utána még egyszer push 

C:\git>git push -u origin master
Counting objects: 3, done.
Delta compression using up to 4 threads.
Compressing objects: 100% (2/2), done.
Writing objects: 100% (3/3), 452 bytes | 452.00 KiB/s, done.
Total 3 (delta 0), reused 0 (delta 0)
To https://github.com/13KESandbox/teszt.git
   e62ef47..a78ff2e  master -> master
Branch 'master' set up to track remote branch 'master' from 'origin'.

11. Nézd meg a Githubon, mit csináltál!

Minden helyi módosítás után commit-olni kell a helyi repoba, majd push a távoliba
Ha a távoli módosul valaki más által, akkorr pull. 

########################################################################################################################




 



