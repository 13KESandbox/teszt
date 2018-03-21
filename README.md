# Git parancssori kezelése

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

9. git remote add origin 


