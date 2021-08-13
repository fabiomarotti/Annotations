# Git 
Repositório com os estudos realizados sobre o Git v2.x e GitHub

- `Git` software de versionamento, nele se realiza os comandos via terminal **Git BASH** para efetuar o versionamento de um projeto.
- `GitHub` é uma plataforma de repositórios remoto que hospeda os codigos-fontes e arquivos de controle de versão usando **Git**. 
  - `GitHub Pages` hospedagem de uma página em HTML, CSS e JavaScript no proprio **GitHub**. [+ detalhes](https://docs.github.com/pt/github/working-with-github-pages/creating-a-github-pages-site)
  - `GitHub Gist` é um serviço do **GitHub* destinado para armazenar arquivos, partes de códigos ou ate mesmo códigos inteiros. [+ detalhes](https://docs.github.com/pt/github/writing-on-github/creating-gists)
- `GitLab` semelhante/concorrente ao **GitHub**, mas permite armazenar código em servidores próprios
- `GitFlow` é um modelo de workflow para estruturar de forma eficiente as _branchs_ um repositório.
  - *Centralized Workflow*: commit local direto na master remote
  - *Feature Branch Workflow* : criar Branch para cada alteração e fazer Merge na master
  - *GitFlow Workflow* : 
  - *Forking Workflow* :
  
- Issues: Tarefas numeradas a serem realizadas
# IDEs para Git
- [GitKraken](https://www.gitkraken.com/)
- [TortoiseGit](https://tortoisegit.org/download/)
- [GitHub Desktop](https://desktop.github.com/)

# Considerações
- GitHub alterou o nome do branch padrão de `master` para `main`
- dependendo da versão do `Git` instalada, o `git init` gerará uma branch `master` ao inves de `main`

## Ciclo de vida de um arquivo no Git
- Arquivo: Não Rastreado (**Untracked**) : (arquivo novo, criado e não add para a Staging)
- Arquivo: Rastreado (**Tracked**)
  - Arquivo: Não modificado (**Unmodified**)
  - Arquivo: Modificado (**Modified**)
  - Arquivo: Preparado (**Staged**)
  - Arquivo: Consolidado (**Commit**)
  - Arquivo: Enviado (**Push**)

## Trabalhando as 4 etapas (Modificar / Preparar / Consolidar / Enviar) 
- Modificar: ***Change***
- Preparar:  **Stage Changes***
- Consolidar: **Coomit**
- Enviar: ***Push***

| Etapas      |  Git                                      | VS Code                     |
|---          |---                                        |---                          |
| Modificar   | Untracked/Tracked file (**git status**)   | ___Changes___               |
| Preparar    | Tracked                   (**git add**)   | ___Stage Changes___ (➕)   | 
| Consolidar  | Commit                 (**git commit**)   |  (✔)                       | 
| Enviar      | Push/ Merge        (**git push/merge**)   | ___PUSH___                 |
<br>


### Configuração

### `git --version` 
- (versão atual do git)

### `git config` 
- `git config` : lista as opções de complemento do comando.
  - `git config --list` : lista todas as variáveis definidas no arquivo de configuração, junto com seus valores.
  - `git config --global -e` : abrir arquivo de configuração em um aeditor de notas.
  - `git config --global user.name "Fábio" ` : setar nome de usuário.
  - `git config --global user.email "fabio@hotmail.com" ` : setar e-mail.
  - `git config [--system, --local, --global]` : opções do arquivo de configuração: sistema, local e global.
 
### `git help`
- `git help` ajuda geral 
  - `git help -a` ajuda específica (tambem se encontra no c:/.../git-doc)

### Iniciando o repositório 
-  Preparando a pasta do projeto para que ela comece a ser versionada pelo Git.
-  Cria-se uma pasta oculta _.git_ onde estará contido o versionamento.
-  Para excluir o versionamento local, basta apagar a pasta _.git_  (isso não excluirá o projeto)
   - comando no PROMPT-DOS para excluir a pasta: `rm -rf .git` (r: deleta subdiretórios, f: força e ignora arquivos não localizados)

### `git init`  
~~~JavaScript
// comando para criar/iniciar o repositório
git init

// para inicar de modo (puro) Servidor
git init --bare
~~~
[+ detalhes sobre --bare](https://pt.stackoverflow.com/questions/80182/qual-%C3%A9-a-diferen%C3%A7a-entre-git-init-e-git-init-bare)


### Associando projeto do Repositório Local com o Repositório Remoto **rever
~~~JavaScript
// associa o projeto do Repositório Remoto ao Repositório Local
// origin: alias utilizado por convencção para o repositório remoto
git remote add origin <URL_projeto>

// puxar informações do Repositorio Remoto
// supoem-se que main seja a branch principal
git pull origin main

// criando/alterando de branch
// -b: cria o branch caso não exista
git checkout -b main

// enviando ao Repositório Remoto
git push origin main
~~~

<br>
--- 
<br>

# Comandos do Git

### `git status`
~~~JavaScript
// verifica se há arquivos Modificados (Untracked File)
// verifica se há arquivos Preparados (Staging Area)
git status
~~~

### `git remote`
~~~JavaScript  
// exibe o alias dos Repositório Remoto (origin por convenção)
git remote

// exibe o alias e as URL de (fetch e push)
git remote -v

// exibi arvore de branchs 
git remote show origin
~~~

### `git fetch`
~~~JavaScript
// baixa/atualiza as referências locais com relações às remotas, mas não faz o merge/incorpora com o branch local
// ou seja, baixa commits, arquivos e referências de um Repositório Remoto para seu Repositório Local 
// para descobrir o alias, use: git remote -v

git fetch  <alias_origin>  <nome_branch>
~~~

* * * * 

### `git cherry pick`
> Situação problema: <br>
> Executar um Merge ou Rebase em um código que ainda não foi finalizado, pode ocasionar problemas por trazer códigos desnecessários. <br>
> Logo, `git cherry-pick` traz apenas um commit especifico, evitando conflitos.
<br>
> Cria-se uma Cópia do commit "copiado", porem com uma nova HASH para o commit "colado"

~~~JavaSCript
// copiar para branch, um commit especifico em outro branch
git cherry-pick <HASH_commit>
~~~


###  `git tag`
> Acrescenta TAG na identificação do ultimo commit <br>
> `git show` exibe o ultimo commit

~~~JavaSCript
// listar tags
git tag

// pesquisar tag especifica, * é complemento
git tag -l "<nome_tag> *" 

// criar tag, marcação leve
git tag <nome_tag>

// criar tag, abre editor de texto para add mais informaçoes
git tag -a <nome_tag>

// cria tag, não abre o editor de texto
git tag -a <nome_tag>  -m  " <mensagem_da_tag> "

// excluir tag
git tag -d <nome_tag>
~~~

###  `git checkout` 
- visualiza as alterações realizadas nos arquivos do passado, podendo executar uma edição no proprio passado.
- realizar o chekout apenas com a _stage changes_ vazia (unstaged), sem nada a commitar

~~~JavaSCript
// acessar uma branch
git checkout <nome_branch>

// acessar um Commit especifico (para pesquisar HASH, use: git log)
git checkout <HASH_do_commit> 

~~~

### `git branch`
~~~JavaScript
//  listar todas as _branchs_ do Repositorio Local
git branch

//  listar todas as _branchs_ do Repositorio Remoto
git branch -a

// cria uma branch
git branch <Nome_da_Nova_Branch>

// cria uma branch e seta
git checkout -b <Nome_da_Nova_Branch>
~~~


### `git log`
> q: para sair

~~~JavaScript
// listar todos os Commits (hash, nome, data, mensagem)
git log    

// listar Commits de um arquivo específico
git log <nome_arquivo.txt>

// listar Commits resumido em uma linha
git log --oneline

// listar arquivos excluidos pelo **rm**
git log --diff-filter=D --summary

// listar colorido
git log --all --decorate --oneline --graph
~~~

[ver+](https://git-scm.com/book/pt-br/v2/Fundamentos-de-Git-Vendo-o-hist%C3%B3rico-de-Commits)

### `git show`
~~~JavaScript
// pesquisa pelo commit especificado pela string hash e as edições efetuadas no arquivo 
//   (3 primeiros caracteres da hash ja são o suficiente para a busca)  
//    sem informar o hash, busca informações do ultimo commit

git show <string_HASH>
~~~

### `git diff`
> informações sobre as alterações realizadas nos arquivos, comparando _changes_ de _stage changes_

~~~JavaScript
// arquivs alterados em _changes_
git diff

// informações do arquivo em particular
git diff <nome_arquivo>

// arquivos alterados em _stage changes_
git diff --staged  
~~~

### Repositório Local

### `git add`  
~~~JavaScript
// adiciona o arquivo ao Stage Changes
git add <nome_arquivo>
~~~

### `git commit`
~~~JavaScript
// Commitar
git commit -m "Criar uma mensagem que represente o conjunto de mudanças realizadas"
~~~

### Repositório Remoto

### `git remote`
~~~
// exibir Alias do Repositorio Remoto
git remote

// exibir detalhes do Repositório Remoto (nomeado por convenção como: Origin)
git remote show <origin_alias>

// exibir endereços (Fetch/Push) do Repositório Remoto
git remote -v

// adicionar Localmente um Repositório Remoto 
// git remote add origin https://...
git remote add <remote_alias> <URL_URI>

//-- rastreia todos os branchs - Fetching
git remote update

~~~

### `git pull`
~~~JavaScript
// Incorpora mudança de um Repositório Remoto para o branch local 
// pull é o modo abreviado de fetch + merge

git pull
~~~

### `git push`
- Executar um `git pull` antes de fazer um `git push`

~~~JavaScript
git push

// Envia para o Repositório Remoto
git push origin master

// enviar para o Repositorio Remoto (para a branch master)
git push -u origin master

// enviar todos os Branchs
git push origin --all
~~~

## Criar uma `branch` 
~~~JavaScript
// criar uma branch no repositorio remoto
git checkout -b <nome_branch>

git branch <nome_branch>
~~~



### `git clone`
~~~JavaScript
//  usar a URL do repositório para realizar uma "copia" do projeto no repositório local
// cria uma cópia com o mesmo nome no repositório de origem
git clone <URL_repositório> 

// cria uma cópia com um nome especifico para pasta
git clone <URL_repositório>  <nome_pasta>
~~~








### `git branch` 
- para acesar uma branch diferente `git checkout <nome_branch>`

~~~JavaScript
// para renomear a branch atual para um novo nome
git branch -m <nome_novo>

// Renomeia o branch Local
git branch -m <nome_atual> <nome_novo>

git push origin HEAD:<nome_branch>

git push --set-upstream origin <nome_branchnovo>

~~~


### `git commit`
~~~JavaScript
// renomear a mensagem do ultimo commit
git commit --amend
~~~

### `git revert` (mais seguro: cria-se um novo)
~~~JavaScript
// reverter o commit especificado pela hash (ver _git log_ )
git revert <HASH_commit>

// reverter o último commit
// reverter um commit_A, na verdade, é realizar um commit_B sem as últimas alterações do commit_A
// HEAD é um ponteiro para o elemento atual

git revert HEAD
~~~

### `git reset` (apaga mesmo e ja éra)

- `--mixed` (padrão) retira os arquivos da _stage changes_ mas não mexe no conteúdo dos arquivos
- `--soft` reseta apenas a HEAD para o commit especificado, deixando em modo _Changes to be commited_
- `--hard` retira os arquivos da _stage changes_ e o seu conteúdo alterado
- `--merge`
- `--keep`
  
~~~JavaScript
// desfaz alterações
git reset 
~~~

# Remover

### `git rm`
~~~JavaScript
// informa  a staging area que o arquivo tem o status de Deleted
// deleta o arquivo do working directory
git rm <nome_arquivo>

// arquivo permanece no working directory apos o commit
// informa que o arquivo deve ser excluido do git directory
// exclui o arquivo da staging area
git rm --cached <nome_arquivo>
~~~  
  
### `git checkout`
~~~JavaScript
// recupera o arquivo apagado pelo rm
git checkout <HASH_commit>
git checkout <nome_arquivo>
~~~

### `git stash`
> Usado quando se quer fazer um *pull* mas existe arquivos sendo trabalhados a parte.
- `git stash apply` : salvar
- `git stash list` : listar
- `git stash clear` : limpart

### `git remote`
[ver+](https://www.atlassian.com/br/git/tutorials/syncing)

~~~JavaScript
// Listar as conexões remotas com outros repositorios
git remote

// Listar as conexões remotas, mas inclui a URL de cada conexão
git remote -v

// add
git remote add <nome> <url>

// remover
git remote rm <name>

// renomear
git remote rename <old-name> <new-name>
~~~

<br> 
----
<br>


# Criando Branchs 
~~~JavaScript
// criar uma Branch
git branch <nome_da_branch>

// -b: crie caso não exista
git checkout <nome_branch>
git checkout -b <nome_da_branch>

// enviar para branch especifica
git checkout <branch_atual> 
git push -u origin <nome_branch_nova>

// mesclar branch principal (onde está) com branch nova
git merge <nome_branch_nova>


// excluir branch
git branch -d <nome_branch_ser_excluida>
~~~


## Criando Forks 
- Cria-se uma copia do projeto de um repositório_1 para o seu repositório_2.
- Criar uma pasta no Repositorio_2 Local/Remoto e fazer um git clone
  
~~~
// copia o repositório_1 pela URL_repositorio
git clone <URL_repositorio>
~~~

~~~
// para enviar o projeto trabalho no repositorio_2 para o repositorio_1
git pull request
~~~


# 5 Em analise




---


# Arquivo `.gitignore`
> `git status` rastreia por arquivos na `Stage Changes` para serem commitados, por isso o arquivo `.gitignore` tem o seu papel de alterar o `git status` criando exceções para que se evite o commit de arquivos indevidos (ou muitos grandes).

- `#` comentários
- `*` nenhum a muitos caracteres 
- `?` um único caractere
- `!` negação da ignoração (permissão) 
- `nome_diretorio/` ignora o diretório e seus aquivos  
- `**/nome_diretorio` ignora o **todos** os diretório e seus aquivos  
- nome dos arquivos/diretórios a serem ignorados são separados por linhas
- [criar arquivo .gitignore](https://www.toptal.com/developers/gitignore) 
  
### Comandos para se criar um arquivo gitignore global
- `git add .gitignore` criar arquivo
- `git commit -m "Arquivo gitignore criado!"`
- `git config --global core.excludesFile ~/.gitignore` criar arquivo global (ignorado por qualquer qualquer repositorio) 
- `git rm -r --cached` substituir arquivo ja existente
  

# Gitflow
- Segundo Vincent Driessen (2010), `Gitflow` é um modelo de branching ao qual se usa para um melhor fluxo de trabalho com o git.
- Modelo para nomear e estrtuturar as `branchs` de um repositório

- `Branch`:
  -  `Master` : Conterá a **versão** principal do repositório
  -  `Develop` : 
  -  `Release`: para realziar testes e validação
  -  `Feature`
  -  `Hotfix`

### GitFlow e Trunk Based Development
- Main
- Develop
- Feature Branch
 
 ### Exemplos para os nomes:
- de `features`:
  - feature/new-botton
  - feature/new-contact-page
  
  
  
  # -- a  ver
  
  - alias graph='git log --all --decorate --oneline --graph'
  - grap
  - git checkout origin/master
  - git fetch origin
  - gir merge origin/main
  - git push = git fetch+merge

<br>
----
<br>
 
# Sequência Básica

> Inicializa a pasta para o Git:
- `git init`

> Analisa quais arquivos foram alterados:
- `git status`

> Adiciona arquivos para Staging Area (preparação do commit):
- `git add <nome_arquivo.txt>` (add arquivo especifico)

- `git add . `                       (add todos: New, Modified, Deleted)
- `git add --all` ou `git add -A`    (add todos: New, Modified, Deleted)
- `git add --ignore-removal .`       (add apenas: New e Modified)
- `git add --update` ou `git add -u` (add apenas: Modified e Deleted)


> Remove/Restaura arquivos da Staging Area (area de preparação para realizar o Commit):
- `git restore --staged <nome_arquivo.txt>` (remove o arquivo da Staging, ou seja, deixa-o no modo Untracked)
- `git restore <nome_arquivo.txt>` (restaura o arquivo modificado (já rastreado mas em Modified) para sua versão anterior)

> Comitar :
- `git commit` (abrirá um editor de texto para informar a mensagem do commit, salvar e fechar executará o commit)
- `git commit -m ` **"Mensagem do Commit"** (apenas commit)
- `git commit -am ` **"Mensagem do Commit com Add"** (add a Staging, apenas arquivos no modo Tracked)

> Lista Commits:
- `git log` (q: sair) (informa: Hash, Autor, Data, Mensagem) 

> Remover/Voltar um Commit:
- `git reset`
  - `git reset --soft` **hash_commit** : volta para o estado antes do commit especificado
  - `git reset --midle` **hash_commit** : igual o soft, porem precisa fazer **git add**
  - `git reset --hard` **hash_commit** : vai para o id do commit e para o resto
  
> Sobre os Repositorios Remotos
- `git remote`   (exibir Alias do Repositorio Remoto utilizado)
- `git remote show <remote>`

> Acessar uma Branch específica:
- `git checkout` **nome_branch__acessar**

> Listar/Criar uma Branch:
- `git branch` (listar todas as Branchs)
- `git branch <nome_branch>`(criar Branch)

> Mostrar o conteúdo das modificações no arquivo:
- `git diff`
- `git diff --name-only` : apenas os nomes dos arquivos modificados
- `git diff` **nome_arquivo** : modificações de um arquivo especifico

----

 git remote add origin [link_repositorio]
 git add [arquivo]
 git reset [arquivo] : remover do index
 git reset --hard    : remover e descartar
 git checkout --[arquivo] : descartar mudanças
 git commit -m "Commit mensagem"  : Comitar
 git commit -am "Commit mensagem" : Adicionar e comitar
 
 
 
 ### branchs
 ## enviar
 git branch [nome-branch] : criar
 git checkout [nome-branch-destine] : mudar de branch
 git cheskout -b [nome-branch-nome] : criar e alternar para branch
 git checkout [HASH-commit] : Alternar para um comita especifico pela HASH
 git push -u origin [nome-branch] : enviar uma nova branch
 git push : Enviar os commits
 
 # receber
- git clone [link-repositorio.git]
- git pull : obtem commits e o branch do repositorio remoto
- git checkout [nome-branch]
 
- git status : mostrar status do workspace
- git status -s : mostrar status do workspace
- git log : mostrar log de commits
- git log --graph --decorate --oneline
  
- git diff
- git diff HEAD
- git diff --staged HEAD~N : diff do workspace
- git diff --staged : diff do index  


### Hooks
- Scripts que são executados antes de um comando (commit, ou pull)
- [ver +](https://git-scm.com/book/it/v2/Customizing-Git-Git-Hooks)

  
# Dicionário
- `Repositório` é a pasta do projeto propriamente dita, esta pasta contem uma _subpasta oculta_ `.git` (ver _git init_)
- `Repositório Local`   (Git)
- `Repositório Remoto`  (GitHub, GitLab, Bitbucket, ...)
- `Remote` : informa o Alias (apelido) do Repositório Remoto, por convensão usa-se: _Origin_
- `origin` é o _alias_ (apelido) para a URL do seu repositório remoto
- `origin/main` espelho do conteudo do repositorio remoto
- `origin/HEAD` espelho do ponteiro HEAD
- `Upstream` : tudo que você insere no git: criar um repositório no git, fazer um commit, fazer um push.
- `Downstream` : tudo que você pega do git: clonar um repositório, fazer um pull.
- `HEAD` : é o "ramo atual" ou Ponteiro [ver+](http://git-scm.com/docs/git-checkout#_detached_head)
- `FETCH_HEAD` é uma referência de curta duração, armazena o SHA1 do commit

- `Untracked` arquivos que não estão sendo rastreados 
- `Staged` (encenado/preparação) area preparatória para se prosseguir com um commit
- `Change` (Mudança) área que mostra arquivos com alterações (qualquer digito digito no arquivo já sera contado como _Change_).
- `Staged Changes` (Mudanças encenada)  área que contem todos os arquivos _change_ e que estão prontos para o seu envio ao repositório, ou prontos para o _commit_

- `stash` : copia temporaria

- `Branch` (ramificação) é um repositório paralelo que o projeto terá de acordo com sua evolução (snapshots) 
  - `Master` ou _branch master_ é a ramificação principal que conterá o projeto final
  - `Develop` ou _branch  develop_ é o nome de um branch ao qual
  - `Release` ou _branch release_ (Lançamento)
  - `Feature` ou _branch feature_ (caracteristica /aspecto)   
  - `Hotfix` ou _branch hotfix_ (conserto urgente) 

- `Commit` (entregar /comprometer) (confirmação de alterações) (fazer uma snapshot) (ter arquivos na sua staging area) é um conjunto de arquivos da _Stage Change_, conterá uma menssagem para descrever sobre esse conjunto de arquivos. 
- `Fetch` (Buscar) : Baixa os commits, arquivos e referências de um repositório remoto para seu repositório local.
- `Merge` (fusão) combinar/fundir a _branch A_ com uma _branch B_
- `Pull` (Puxar) é uma atualização local, que puxa do repositorio remoto os arquivos mais recentes para repositorio local. (git pull é uma combinação de comandos: git fetch e git merge).
- `Push` (Empurrar) é o envio final de um conjunto de _commits_ para o repositório
- `Clone` (células geneticamente idênticas)
- `Checkout` (Conferir) Verifica os arquivos e commits a serem..
- `Fork` (Bifurcação /garfo) é um clone interno ao github
- `Pull Request`(Requisição de envio) é um pedido 
- `Status` (posição /condição)
- `forking` uma copia do projeto para ser trabalhada por outras pessoas, e futuramente redistribuir pro dono do projeto origianl.


 
## Referências
- https://git-scm.com/book/en/v2
- https://git-scm.com/
- https://github.com/
- https://gist.github.com/discover
- https://docs.github.com/en/github/searching-for-information-on-github/searching-code
- https://git-scm.com/book/pt-br/v2/Fundamentos-de-Git-Trabalhando-de-Forma-Remota
- https://pt.slideshare.net/fernandomdr/controle-de-versao-e-colaboracao-com-git?fbclid=IwAR1FtaD0u6S70xcFMTqcjAIkbHQ0KPFRhJshAfusNm0doFawGUG5eVTr5Qs
- https://www.youtube.com/watch?v=OuOb1_qADBQ
- https://blog.cedrotech.com/git-o-minimo-que-voce-precisa-saber-para-trabalhar-em-equipe-parte-2
- [Resumo dos Comandos - Oficial](https://training.github.com/downloads/pt_BR/github-git-cheat-sheet.pdf)
