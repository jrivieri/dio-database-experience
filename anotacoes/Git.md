#**Git / GitHub**
***

*no ubuntu, está instalado como padrão a versão 2.25 e para atualizar para a versão atual:*

```add-apt-repository ppa:git-core/ppa```
```apt update```
```apt install git```


**SHA1 – Secure Hash Algorithm** – gera um conjunto de caracteres indentificador de 40 dígitos
gerar chave para a palavra “ola mundo”:

```echo “ola mundo” | openss l sha1```

gerar chave para o conteúdo do arquivo texto.txt:
```openssl sha1 texto.txt```

*obs.: a cada alteração de conteúdo do texto, é gerado uma nova chave*

***

**Tipos Básicos de Objetos no Git:**

##**Blobs – objeto básico**


```echo “conteudo” | git hash-object –stdin```
ou
```echo -e “blob 9\0conteudo” | openssl sha1```

**Tree** – armazena os Blobs
* pode apontar para outra árvore
* se mudar o sha1 de um arquivo/blob, irá mudar o sha1 da árvore

**Commit** – aponta para o tree, parente, autor e contém mensagem e timestamp
* possui hash de toda a informação
* se alterar o blob, altera a tree, que altera o commit

***

##**Chave SSH e Token**

*para criar a chave:*
```sudo ssh-keygen -t ed25519 -C alrivierijr@gmail.com```

*será solicitado o nome que será criado na pasta do usuário antonio/.ssh*
*colar no github, somente o conteúdo da chave pública*

```eval $(ssh-agent -s)```
*usado para gerar o agente que vai manter a chave na memória*

```ssh-add nomeArquivo```

*obs.: se não executar, tente executar o comando antes:*
```sudo exec ssh-agent bash```

criar o repositório no github e pegar o link ssh.

No bash, digitar:  
```git clone  linkSshDoGithub```

***

##**Comandos Git**

```git init```

```	git config –global user.email “usario@dominio.com”```
```	git config –global user.name “usuarioNome”```

```git add .```
```git commit -m “mensagem”```

***

*para listar a configuração do git na máquina:*
```git config - -list```

*Se precisar excluir o nome e senha da configuração do git:*
```git config --global --unset user.email```
```git config --global --unset user.nome```
*e incluir novamente essas configurações:*

```git config –global user.email “usuarioNovo@dominioNovo.com”```
```git config –global user.name “nomeNovo”```

*Criar um repositório no gitHub, depois enviar o repositório local:*

```git remote add origin git@github.com:usuario/projeto.git```
```git branch -M main```
```git push -u origin main```

*Lista a origem do repositório que foi copiado:*
```git remote -v```]

****