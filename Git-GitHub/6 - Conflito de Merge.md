# Conflito de Merge

Ocorre quando alguém clona seu repositório e passa a editar na mesma linha de código que você. Ao ser empurrado para o GitHub, o sistema remoto acusa o conflito. O conflito de merge também pode ser ocasionado quando você faz alguma edição diretamente no GitHub e depois tenta empurrar uma posterior edição feita do repositório local. Isso ocorre porque o commit gerado no git do servidor do GitHub está mais atualizado e não é transferido automaticamente para seu repositório local. Veja um exemplo do problema abaixo e como resolvê-lo.

![Conflito de Merge](https://user-images.githubusercontent.com/84105393/160909026-56e89278-904d-493d-9431-20607827463d.png)

~~~git
Eu@Patricia MINGW64 /c/workspace/livro-receitas (master)
$ git push origin master
To https://github.com/bikindev/livro-receitas.git
 ! [rejected]        master -> master (fetch first)
error: failed to push some refs to 'https://github.com/bikindev/livro-receitas.git'
hint: Updates were rejected because the remote contains work that you do
hint: not have locally. This is usually caused by another repository pushing
hint: to the same ref. You may want to first integrate the remote changes
hint: (e.g., 'git pull ...') before pushing again.
hint: See the 'Note about fast-forwards' in 'git push --help' for details.

Eu@Patricia MINGW64 /c/workspace/livro-receitas (master)
$ git pull origin master
remote: Enumerating objects: 5, done.
remote: Counting objects: 100% (5/5), done.
remote: Compressing objects: 100% (3/3), done.
remote: Total 3 (delta 1), reused 0 (delta 0), pack-reused 0
Unpacking objects: 100% (3/3), 707 bytes | 28.00 KiB/s, done.
From https://github.com/bikindev/livro-receitas
 * branch            master     -> FETCH_HEAD
   3a69ac7..db9f803  master     -> origin/master
Auto-merging README.md
CONFLICT (content): Merge conflict in README.md
Automatic merge failed; fix conflicts and then commit the result.
~~~
