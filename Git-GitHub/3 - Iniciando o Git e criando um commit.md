# Iniciando o Git e criando um commit

* __Git init:__ comando que inicia o Git e cria um repositório em um determinado diretório;
* __Git add:__ move arquivos e dá início ao versionamento;
* __Git commit:__ cria o commit.

Flag “-a”: mostra pastas ocultas (deve vir após o comando dir ou ls), por exemplo, para mostrar a pasta gerencial do Git criada num dado diretório com o comando git init.

__Ao iniciar o Git pela primeira vez, é necessário setar algumas configurações que serão necessárias para a criação do commit.__ São elas e-mail e nome. Você pode configurar essas infos como globais ou apenas como individuais, para que serviam apenas para o repositório que você está criando.

~~~git
Eu@Patricia MINGW64 /c/workspace/livro-receitas (master)
$ git config --global user.email "patriciasouzacouto.92@gmail.com"

Eu@Patricia MINGW64 /c/workspace/livro-receitas (master)
$ git config --global user.name Bikin
~~~

Em seguida, iniciamos o git (com o git init) naquele diretório, criando, assim, um repositório.

~~~git
Eu@Patricia MINGW64 /c/workspace/livro-receitas (master)
$ git init
Eu@Patricia MINGW64 /c/workspace/livro-receitas (master)
$ git add *
Eu@Patricia MINGW64 /c/workspace/livro-receitas (master)
$ git commit -m "commit inicial"
[master (root-commit) e764ed6] commit inicial
 2 files changed, 58 insertions(+)
 create mode 100644 Espaguete com molho de cogumelo e pimenta vermelha.md
 create mode 100644 espaguete_com_molho_de_cogumelo
~~~
