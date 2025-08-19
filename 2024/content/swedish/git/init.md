---
title: Skapa nytt repo i detalj
weight: 25
---

Vi skall nu titta lite mer i detalj vad som händer när vi skapar ett nytt Git
repo. 

## Skapa en ny katalog

För att skapa ett nytt repo navigerar du i terminalen till den katalog du
vill göra till ett repo. Sedan utför du kommandot `git init`. I följande
exempel skapas först katalogen `git-init-test` med kommandot `mkdir`.

``` shell
 $> mkdir git-init-test
```

## Kliv in i den nya katalogen 

Använd kommandot `cd` för att gå in i den nya katalogen. 


``` shell
$> cd git-init-test
```

## Kika om katalogen är tom 

Vi kan använda kommandot `tree` för att se om den nya katalogen är tom. 

``` shell
$> tree
```

Mycket riktigt är katalogen tom. 

``` shell
.

0 directories, 0 files
```

## Initiera ett nytt Git repo

Nu initierar vi ett nytt Git repo i den nya katalogen med kommandot `git init`.

``` shell
 $> git init
```

Om det går bra svarar Git med något liknade detta. 

``` shell
Initialized empty Git repository in ~/git-init-test/.git/
```

Notera `.git` på slutet av sista raden ovan. Vi kommer återkomma till `.git`
alldeles strax. 

## Kolla om katalogen fortfarande tom

Vi prövar igen med kommandot `tree` för att se om katalogen
fortfarande är tom.

``` shell
$> tree
```

Konstigt, katalogen verkar fortfarande tom. 

## Git har lagt till en dold katalog

Att katalogen fortfarande verkar vara tom beror på att Git lagt till en
dold underkatalog. I Linux börjar namnet på alla dolda kataloger med `.`. När
i skapade det nya repot talade Git om följande för oss. 
 
 ``` shell
Initialized empty Git repository in ~/git-init-test/.git/
```

Detta betyder att Git lagt till den dolda katalogen `.git` som underkatalog
till katalogen `git-init-test` som vi skapat ett nytt repo i. 
För att `tree` skall ta med även dolda kataloger behöver vi
 lägga till flaggan `-a` (view all). Genom att även lägga till flaggan `-F`
 kommer symbolen `/` att läggas till efter namnet på kataloger så vi enkelt kan
 skilja på vanliga filer och kataloger.  
 
 ``` shell
$> tree -a -V
```
Nu ser vi den dolda katalogen `.git` och alla mappar och filer som ligger under
katalogen `.git` som ett träd. 

``` shell
.
└── .git/
    ├── branches/
    ├── config
    ├── description
    ├── HEAD
    ├── hooks/
    │   ├── applypatch-msg.sample*
    │   ├── commit-msg.sample*
    │   ├── fsmonitor-watchman.sample*
    │   ├── post-update.sample*
    │   ├── pre-applypatch.sample*
    │   ├── pre-commit.sample*
    │   ├── prepare-commit-msg.sample*
    │   ├── pre-push.sample*
    │   ├── pre-rebase.sample*
    │   ├── pre-receive.sample*
    │   └── update.sample*
    ├── info/
    │   └── exclude
    ├── objects/
    │   ├── info/
    │   └── pack/
    └── refs/
        ├── heads/
        └── tags/

10 directories, 15 files
```

Det är med hjälp av innehållet i den dolda katalogen `.git` som Git håller reda
på staging area och historiken för repot. Ett Git repo är en helt vanligt
katalog och det som gör det till ett Git repo är allt innehåll i den dolda
mappen `.git`. 
Av innehållet i den dolda katalogen `.git` kan vi lägga på minnet att det finns
en underkatalog som heter `branches` (grenar).

## Kolla status

Vi prövar att se vad som händer om vi kollar status på vårt nya repo. 

``` shell
$> git status
```

Eftersom vi varken lagt till några filer gjort några commits svarar Git så här. 

``` shell
On branch master

No commits yet

nothing to commit (create/copy files and use "git add" to track)
```

## Kolla loggen 

Vi provar att se om det finns något i loggen. 

``` shell
$> git log
```

Som väntat finns inget att visa i loggen. 

``` shell
fatal: your current branch 'master' does not have any commits yet
```

## Vad händer om man tar bort .git?

Tar man bort katalogen `.git`  kommer alla vanliga filer och mappapar i
katalogen `git-init-test` fortfarande att finnas kvar. Det enda som försvinner
är all information om Git repot med all historik och annan information som Git
använder sig av. 

Vi tar bort katalogen `.git` med kommandot `rm` (remove). Vi behöver lägga till
flaggan `-r` för att rekursivt ta bort alla underkataloger under `.git`och `-f`
för att slippa svara ja/nej för varje fil/mapp som tas bort. 

``` shell
$> rm -rf .git
```

Vi prövar igen med `git status` och `git log.`

``` shell
$> git status
```

Du bör nu se något liknade detta i terminalen. 

``` shell
fatal: not a git repository (or any of the parent directories): .git
```

Vi prövar med `git log` igen. 
``` shell
$> git log
```

Du bör nu se något liknade detta i terminalen. 

``` shell
fatal: not a git repository (or any of the parent directories): .git
```

Efter att vi tagit bort `.git` kan katalogen `git-init-test` inte längre fungera som ett
Git repo. 

