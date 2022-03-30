# Ciclo de vida dos arquivos no Git

![Ciclo de vida dos arquivos no Git](https://user-images.githubusercontent.com/84105393/160907786-ed50c51e-9fde-492a-bdf1-891ea86a0692.png)

* O git init inicializa um repositório vazio na pasta em questão

* Untracked é um arquivo que o git ainda não “visualiza” (ainda não gerencia/monitora), pois ainda não foi adicionado ao git (o repositório ainda não foi criado). Ao ser adicionado ao git, por meio do comando git init, o arquivo passa a ser reconhecido -> tracked.

* Staged é um estado no qual o arquivo fica aguardando ser comitado, está em modo temporário. Um arquivo se torna staged quando o comando git add é iniciado.

* Ao receber o comando commit, os arquivos stageds se tornam permanentes e podem finalmente ir para o palco brilhar!!! Se apagarmos um arquivo que foi adicionado, porém não comitado (está na fase staged), por exemplo, ao tentar realizar um novo commit, não será gerado um novo SHA-1, pois essa mudança não foi declarada permanente.
