# Git
Repositório com os estudos realizados sobre o Git e Github

- `Git` software de versionamento, nele se realiza os comandos via terminal **Git BASH** para efetuar o versionamento de um projeto.
- `Github` é uma plataforma de repositórios remoto que hospeda os codigos-fontes e arquivos de controle de versão usando **Git**. 
- `Github Pages` hospedagem de uma página em HTML, CSS e JavaScript no proprio **Github**. [+ detalhes](https://docs.github.com/pt/github/working-with-github-pages/creating-a-github-pages-site)
- `Github Gist` é um serviço do **Github* destinado para armazenar arquivos, partes de códigos ou ate mesmo códigos inteiros. [+ detalhes](https://docs.github.com/pt/github/writing-on-github/creating-gists)
- `Gitflow` é um modelo de workflow para estruturar de forma eficiente as _branchs_ um repositório.
- `GitLab` semelhante/concorrente ao **Github**, mas permite armazenar código em servidores próprios

# Considerações
- Repositório Local
- Repositório Remoto  (Github)
- HEAD é um ponteiro
- [Resumo dos Comandos - Oficial](https://training.github.com/downloads/pt_BR/github-git-cheat-sheet.pdf)


## Fluxo de trabalho geral 

> (master) - > `branch/snapshots` -> (versão_projeto) -> `merge` -> (master)
> - `Branch` : cria uma ramificação para realizar alterações no projeto.
> - `Merge` : recebe uma ramificação para acrescentar ao projeto. 
> <br>

## Ciclo de vida de um arquivo no Git

- Não Rastreado (`Untracked`)
- Rastreado (`Tracked`)
  - Não modificado (`Unmodified`)
  - Modificdo (`Modified`)
  - Preparado (`Staged`)
  - Consolidado (`Commit`)
  - Enviado (`Push/Merge`)


- 4 etapas para o envio (Modificar / Preparar / Consolidar / Enviar)

| Etapas      |  Git                           | VS Code                    |
|---          |---                             |---                         |
| Modificar   | Untracked/Tracked file         | ___Changes___              |
| Preparar    | Tracked              (git add) | ___Stage Changes___ (➕)  | 
| Consolidar  | Commit            (git commit) |  (✔)                      | 
| Enviar      | Push/ Merge   (git push/merge) | ___PUSH___                |
<br>


# Comandos Git
### Configuração

### `config` 
- `git config`
  - `git config --global user.name "Fábio" `
  - `git config --global user.email "fabio@hotmail.com" `
  - `git config --list`

### `help`
- `git help` ajuda geral 
  - `git help -a` ajuda específica (tambem se encontra no c:/.../git-doc)


## Iniciando o repositório 
-  Preparando a pasta do projeto para que ela comece a ser versionada pelo Git.
-  Cria-se uma pasta oculta _.git_ onde estará contido o versionamento.
-  Para excluir o versionamento local, basta apagar a pasta _.git_  (isso não excluirá o projeto)
   - `rm -rf .git` comando no PROMPT para excluir a pasta (r: deleta subdiretórios, f: força, ignora arquivos não localizados)

### `init`  
~~~JavaScript
// comando para iniciar o repositório
git init

// para inicar de modo (puro) Servidor
git init --bare
~~~
[+ detalhes sobre --bare](https://pt.stackoverflow.com/questions/80182/qual-%C3%A9-a-diferen%C3%A7a-entre-git-init-e-git-init-bare)

- OBS.: 
- Github alterou o nome do branch padrão de `master` para `main`
- dependendo da versão do `Git` instalada, o `git init` gerará uma branch `master` ao inves de `main`

### Associando projeto Local com Remoto
~~~JavaScript
// cmando associa o projeto remoto ao Local
git remote add origin <URL_projeto>

// atualizar
git pull origin main

// criando/alterando de branch
// -b: crie o branch caso não exista
git checkout -b main

// enviando ao repositorio Remoto
git push origin main

~~~




# 0) Análise / Consultas

### `status`
~~~JavaScript
// verifica se há arquivos Modificados (Untracked file)
// verifica se há arquivos Preparados (Stage area)
git status
~~~

### `branch`
~~~JavaScript
//  listar todas as _branchs_ do Repositorio Local
git branch

//  listar todas as _branchs_ do Repositorio Remoto
git branch -a
~~~

### `remote`
~~~JavaScript  
// exibe os repositórios remotos
// estar dentro da para executar o comando
// nome padrão: Origin

git remote

// lista de forma especificada
git remote -v
~~~

~~~JavaScript
// mostrar detalhes da branch remota
git remote show origin
~~~

###  `checkout` 
- visualiza as alterações realizadas nos arquivos do passado, podendo executar uma edição no proprio passado.
- realizar o chekout apenas com a _stage changes_ vazia (unstaged), sem nada a commitar

~~~JavaSCript
// (ver _git log_)
git chekout <HASH_commit> 
~~~

~~~JavaScript
// volta para o estado atual e mais recente
git chekout master
~~~


### `log`
~~~JavaScript
// verifica se há arquivos _commitados_ ( log de commites: hash, nome, email, data, mensagem do commit)
git log    

// mostrar histórico de commits que envolveram o nome_arquivo
git log <nome_arquivo>

// mostrar histórico de commits de forma resumida 
git log --oneline

// busca de arquivos excluidos pelo **rm**
git log --diff-filter=D --summary
~~~

### `show`
~~~JavaScript
// pesquisa pelo commit especificado pela string hash e as edições efetuadas no arquivo 
//   (3 primeiros caracteres da hash ja são o suficiente para a busca)  
//    sem informar o hash, busca informações do ultimo commit

git show <string_HASH>
~~~

### `diff`
> informações sobre as alterações realizadas nos arquivos, comparando _changes_ de _stage changes_

~~~JavaScript
// arquivs alterados em _changes_
git diff

// informações do arquivo em particular
git diff <nome_arquivo>

// arquivos alterados em _stage changes_
git diff --staged  
~~~



# 1) Envio

## Trabalhando as 4 etapas (Modificar / Preparar / Consolidar / Enviar) 
- Modificar: ***Change***
- Preparar:  **Stage Changes***
- Consolidar: **Coomit**
- Enviar: ***Push***

### Repositório Local

### `add`  
~~~JavaScript
// adiciona o arquivo ao Stage Changes
git add <nome_arquivo>
~~~

### `commit`
~~~JavaScript
// Commitar
git commit -m "Criar uma mensagem que represente o conjunto de mudanças realizadas"
~~~

### Repositório Remoto

### `push`
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
~~~


# 2) Recebimento

### `clone`
~~~JavaScript
//  usar a URL do repositório para realizar uma "copia" do projeto no repositório local
// cria uma cópia com o mesmo nome no repositório de origem
git clone <URL_repositório> 

// cria uma cópia com um nome especifico para pasta
git clone <URL_repositório>  <nome_pasta>
~~~

### `remote`
~~~
// adicionar Localmente um repositório Remoto 
git remote add <nome_curto_rep_remoto> <URL_repositorio>

// atualizar
git pull origin master
~~~

### `fetch`
~~~JavaScript
// Baixa as referências de um Repositório Remoto via nome_curto (sem fazer merge)
// <nome_curto> ver: git remote -v

git fetch <nome_curto>

// fetch + merge = pull
git fetch <nome_curto>
git merge FETCH_HEAD
~~~

### `pull`
~~~JavaScript
// Incorpora mudança de um Repositório Remoto para o branch local 
// pull é o modo abreviado de fetch + merge

git pull
~~~



# 3) Edição
### `branch` 
- para acesar uma branch diferente `git checkout <nome_branch>`

~~~JavaScript
// para renomear a branch atual para um novo nome
git branch -m <nome_novo>

// Renomeia o branch Local
git branch -m <nome_atual> <nome_novo>

git push origin HEAD:<nome_branch>

git push --set-upstream origin <nome_branchnovo>

~~~


### `commit`
~~~JavaScript
// renomear a mensagem do ultimo commit
git commit --amend
~~~

### `revert` (mais seguro: cria-se um novo)
~~~JavaScript
// reverter o commit especificado pela hash (ver _git log_ )
git revert <HASH_commit>

// reverter o último commit
// reverter um commit_A, na verdade, é realizar um commit_B sem as últimas alterações do commit_A
// HEAD é um ponteiro para o elemento atual

git revert HEAD
~~~

### `reset` (apaga mesmo e ja éra)

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

### `rm`
~~~JavaScript
// informa  a staging area que o arquivo tem o status de Deleted
// deleta o arquivo do working directory
git rm <nome_arquivo>

// arquivo permanece no working directory apos o commit
// informa que o arquivo deve ser excluido do git directory
// exclui o arquivo da staging area
git rm --cached <nome_arquivo>
~~~  
  
### `checkout`
~~~JavaScript
// recupera o arquivo apagado pelo rm
git checkout <HASH_commit>
git checkout <nome_arquivo>
~~~




# 4) Ramificações

## Criando Branchs 
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
  -  `Release`
  -  `Feature`
  -  `Hotfix`
 
 
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
  - 
  
  
  
  
# Dicionário

- `Untracked` arquivos que não estão sendo rastreados 

- `Repositório` é a pasta do projeto propriamente dita, esta pasta contem uma _subpasta oculta_ `.git` (ver _git init_)

- `Branch` são as ramificações que o projeto terá de acordo com sua evolução (snapshots)
  - `Master` ou _branch master_ é a ramificação principal que conterá o projeto final
  - `Develop` ou _branch  develop_ é o nome de um branch ao qual
  - `Release` ou _branch release_ (Lançamento)
  - `Feature` ou _branch feature_ (caracteristica /aspecto)   
  - `Hotfix` ou _branch hotfix_ (conserto urgente) 

- `Change` (Mudança) área que mostra arquivos com alterações (qualquer digito digito no arquivo já sera contado como _Change_).
- `Staged Changes` (Mudanças encenada)  área que contem todos os arquivos _change_ e que estão prontos para o seu envio ao repositório, ou prontos para o _commit_
- `Commit` (entregar /comprometer) é um conjunto de arquivos da _Stage Change_, conterá uma menssagem para descrever sobre esse conjunto de arquivos.

- `Pull` (Puxar) é uma atualização local, que puxa do repositorio os arquivos mais recentes
- `Push` (Empurrar) é o envio final de um conjunto de _commits_ para o repositório
- `Clone` (células geneticamente idênticas)
- `Checkout` (Conferir) Verifica os arquivos e commits a serem..

- `Fork` (Bifurcação /garfo) é um clone interno ao github
- `Pull Request`(Requisição de envio) é um pedido 

- `Merge` (fusão) combinar /fundir a _branch A_ com uma _branch B_

- `Status` (posição /condição)

- `forking` uma copia do projeto para ser trabalhada por outras pessoas, e futuramente redistribuir pro dono do projeto origianl.

- `fetch`
- `stash`

## Referências

- https://git-scm.com/
- https://github.com/
- https://gist.github.com/discover
- https://docs.github.com/en/github/searching-for-information-on-github/searching-code
- https://git-scm.com/book/pt-br/v2/Fundamentos-de-Git-Trabalhando-de-Forma-Remota
