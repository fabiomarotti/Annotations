# GitFlow


- `Branch` (ramificação) é um repositório paralelo ao qual o projeto terá de acordo com sua evolução (snapshots) 
  - `Master/Main` ou _branch master_ é a ramificação principal que conterá o projeto final.
    - `Tag` é o versionamento do projeto final.
  - `Develop` ou _branch  develop_ é a ramificação para o desenvolvimento.
  - `Release` ou _branch release_ (Lançamento) é a ramificação para testes e validações.
  - `Feature` ou _branch feature_ (caracteristica /aspecto) é a ramificação para novas funcionalidades.
  - `Hotfix` ou _branch hotfix_ (conserto urgente) é a ramificação para atualizações realizadas na master.

<img src="https://github.com/fabiomarotti/Annotations/blob/main/Git/GitFlow/img/img_gitflow.png"  width="1024" height="" />
<div align="center"> Figura 1: GitFlow </div>
<br />

# Trunk Based Development

- `Branch` (ramificação) é um repositório paralelo ao qual o projeto terá de acordo com sua evolução (snapshots) 
  - `Master/Main` ou _branch master_ é a ramificação principal que conterá o projeto final.
    - `Commit` ou _cherry-pick_ insere um commit da Main para Release.
  - `Feature` ou _branch feature_ (caracteristica /aspecto) é a ramificação para novas funcionalidades.
  - `Release` ou _branch release_ (Lançamento) é a ramificação para testes e validações.
    - `Tag` é o versionamento do projeto final.  
  
<img src="https://github.com/fabiomarotti/Annotations/blob/main/Git/GitFlow/img/img_trunk_pick.png"  width="1024" height="" />
<div align="center"> Figura 2: Trunk Based Development </div>
<br />
