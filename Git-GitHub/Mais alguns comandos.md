# Mais alguns comandos

**git status:** mostra o status dos arquivos e árvores do repositório, como o que está untracked, o que foi modificado, novos arquivos, arquivos deletados etc. Mostra tudo que foi feito no repositório após o último commit.
**git config --list:** lista das configurações do git, incluindo o e-mail e nome de usuário setados por você.
**git config --global --unset user.email (ou user.name):** unseta e-mail ou nome de usuário configurados. Basta rodar o código para setar outro e-mail ou nome.
**git add --u:** a flag u atualiza todas as alterações feitas no repositório (ou seja, as envia à área de stage para serem, posteriormente, comitadas. Útil se, ao rodar a função add, os arquivos deletados do disco ainda continuam aparecendo no repositório.

## Movendo arquivos para uma nova pasta

~~~git
Eu@Patricia MINGW64 /c/workspace/livro-receitas (master) //cria novo diretório
$ mkdir receitas

Eu@Patricia MINGW64 /c/workspace/livro-receitas (master) //mostra o que há no diretório
$ ls
'Espaguete com molho de cogumelo e pimenta vermelha.md'   receitas/ //dir criado
 receita.md

Eu@Patricia MINGW64 /c/workspace/livro-receitas (master)
$ mv Espaguete\ com\ molho\ de\ cogumelo\ e\ pimenta\ vermelha.md ./receitas/   //movendo o arquivo para dentro do novo diretório criado

Eu@Patricia MINGW64 /c/workspace/livro-receitas (master)
$ ls
receita.md  receitas/  //observe que o arquivo já não está mais dentro do dir livro-receitas

Eu@Patricia MINGW64 /c/workspace/livro-receitas (master)
$ cd receitas

Eu@Patricia MINGW64 /c/workspace/livro-receitas/receitas (master)
$ ls
'Espaguete com molho de cogumelo e pimenta vermelha.md'
~~~
