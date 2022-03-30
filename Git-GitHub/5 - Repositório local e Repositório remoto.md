# Repositório local e Repositório remoto

* Ambiente de desenvolvimento (pc)
  1. Working directory (working tree)  --git add >>
  2. Staging área  --git commit –m >>
  3. Local repository

* Servidor
  1. Remote repository (ex: GitHub)
  2. O repositório local pode ser enviado para o remoto ou também podemos vincular outros repositórios remotos a ele


## Empurrando o repositório local para um remoto:

Mantenha sempre o mesmo e-mail e nome no repositório local e remoto.


~~~git
Eu@Patricia MINGW64 /c/workspace/livro-receitas (master)
$ git remote add origin https://github.com/bikindev/livro-receitas.git

Eu@Patricia MINGW64 /c/workspace/livro-receitas (master)
$ git remote -v
origin  https://github.com/bikindev/livro-receitas.git (fetch)
origin  https://github.com/bikindev/livro-receitas.git (push)

Eu@Patricia MINGW64 /c/workspace/livro-receitas (master)
$ git push -u origin master
Enumerating objects: 18, done.
Counting objects: 100% (18/18), done.
Delta compression using up to 3 threads
Compressing objects: 100% (16/16), done.
Writing objects: 100% (18/18), 2.22 KiB | 283.00 KiB/s, done.
Total 18 (delta 6), reused 0 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (6/6), done.
To https://github.com/bikindev/livro-receitas.git
 * [new branch]      master -> master
Branch 'master' set up to track remote branch 'master' from 'origin'.
~~~

* Com __“git remote add origin”__ apontamos nosso repositório local para o remoto. E com __“git push origin master (ou main)”__ empurramos o repositório local para o remoto.
* origin é apenas um nome que damos para a url que vai receber o repositório. Qualquer nome pode ser utilizado, mas origin é uma convenção;
* __remote --v__: lista meus repositórios remotos cadastrados. Esta função mostra os repositórios remotos que recebem o repositório tratado.

## Clonar um repositório remoto: Git clone

Comando utilizado para clonar um repositório remoto para nosso repositório local. Útil para se trabalhar nele com o sistema de versionamento. Ao baixar o repositório como arquivo zip, ele vem apenas na forma de diretório, dessa forma não é possível versionar os arquivos.

~~~git
Eu@Patricia MINGW64 /c/workspace/livro-receitas (master)
$ git clone https://github.com/python/cpython.git  //basta colar a url do repositório que deseja clonar
Cloning into 'cpython'...
remote: Enumerating objects: 841464, done.
remote: Counting objects: 100% (633/633), done.
remote: Compressing objects: 100% (347/347), done.
remote: Total 841464 (delta 412), reused 451 (delta 286), pack-reused 840831
Receiving objects: 100% (841464/841464), 372.02 MiB | 1.70 MiB/s, done.
Resolving deltas: 100% (667862/667862), done.
Updating files: 100% (4519/4519), done.
~~~
