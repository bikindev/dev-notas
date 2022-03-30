# Objetos fundamentais do Git

## O SHA-1

O hash SHA-1 é um algoritmo de encriptação que retorna um conjunto de 40 caracteres identificadores. É uma encriptação dos meta dados contidos dentro de objetos. É utilizado para identificar arquivos.  

* __Terminal Git Bash:__
~~~git
Eu@Patricia MINGW64 ~/Desktop
$ openssl sha1 texto.txt
SHA1(texto.txt)= 21ee37574838e2733abaeb1a31251c513baed724
~~~

~~~git
Eu@Patricia MINGW64 ~/Desktop
$ echo 'conteudo' | git hash-object --stdin
fc31e91b26cf85a55e072476de7f263c89260eb1
~~~

A barra reta indica a sequência de um comando (função). Se utilizarmos esta função do git, ela vai nos devolver o sha1 da string ‘conteudo’. –stdin é um indicador de que ‘conteudo’ é um arquivo de texto a ser mostrado ao usuário (esta função espera receber um arquivo). 

~~~git
Eu@Patricia MINGW64 ~/Desktop
$ echo -e 'conteudo' | openssl sha1
(stdin)= 65b0d0dda479cc03cce59528e28961e498155f5c
~~~

Por que o hash foi diferente se o conteúdo é o mesmo? Por causa dos objetos do Git.

----------

## Objetos do Git

* __Blob:__ o Git manipula informações através de objetos. Assim, os arquivos criados no Git (como o do exemplo git hash-object) ficam guardados num objeto chamado Blob, que contém meta dados. É nele que está contido o SHA-1. Um objeto Blob recebe e guarda as seguintes informações (meta dados):
1. O tipo de objeto
2. O tamanho do arquivo
3. \0
4. Conteúdo do arquivo

_Blobs possuem SHA-1._

~~~git
Eu@Patricia MINGW64 ~/Desktop
$ echo -e 'blob 9\0conteudo' | openssl sha1
(stdin)= fc31e91b26cf85a55e072476de7f263c89260eb1
~~~

_Note que agora o SHA-1 corresponde ao criado na função do git._

* __Tree:__ é um objeto que armazena e aponta tipos de blobs ou que aponta para outras árvores. Da mesma forma que dentro de um diretório pode haver outro diretório. Também contém meta dados:
1. Tamanho
2. \0
3. Blobs (SHA-1) ou trees (SHA-1)
4. Nome do arquivo (com extensão)

_Árvores também possuem SHA-1. Logo, se há uma modificação no conteúdo do blob contido no tree, consequentemente o SHA-1 do blob e o SHA-1 do tree mudam._

* __Commit:__ é um objeto que aponta para as árvores. Ele é criado pelo autor de cada repositório, contendo o nome do autor, a data e hora de criação e uma mensagem que explica a função daquele repositório. Um commit apresenta também um SHA-1, que é o hash de todas as informações de todos esses meta dados. Um outro meta dado contido no commit é o parente. A cada vez que um arquivo é alterado, alterando assim o SHA-1 do blob, da árvore e do commit, gera-se um novo commit, com o histórico do commit anterior salvo pelo seu SHA-1. Esse commit anterior é o parente do novo commit (atual). Dessa forma, pode-se ver qualquer mudança feita no repositório por meio da análise do histórico de um commit. Os meta dados de um commit são:
1. Tamanho
2. Trees (SHA-1)
3. Parente (SHA-1)
4. Autor
5. Mensagem
6. Timestamp (data e hora da criação)
