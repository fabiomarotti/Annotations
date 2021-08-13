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

> O trabalho é fundamentalmente realizado nas branchs *Main* e *Develop*. 
> Cada funcionalidade será realizada na branch *Feature*, lembrando que a *Feature* é sempre baseada na branch *Develop*.
> O `Pull Request` é realizado com a passagem da *Feature Branch* para *Develop*. 
> A *Realease Branch* recebe uma copia da branch *Develop* para que possam serem feitas os testes e validações.
> A validações são retornada com `Pull Request`, tanto para *Develop* como para *Master*. 
> Na *Master* são ralizadas *Tags* que marcam os `Pull Request` vindo da *Realease*. 
> Para _bugs_ encontrados na *Main*, cria-se uma branch *Hotfix*, derivada da *Master* (com tag) ao qual seram realizadas as correções e em seguida seram enviadas para *Develop* e *Master*. 
<br />
<br />


# Trunk Based Development

- `Branch` (ramificação) é um repositório paralelo ao qual o projeto terá de acordo com sua evolução (snapshots) 
  - `Master/Main` ou _branch master_ é a ramificação principal que conterá o projeto final.
    - `Commit` ou _cherry-pick_ insere um commit da Main para Release.
  - `Feature` ou _branch feature_ (caracteristica /aspecto) é a ramificação para novas funcionalidades.
  - `Release` ou _branch release_ (Lançamento) é a ramificação para testes e validações.
    - `Tag` é o versionamento do projeto final.  
  
<img src="https://github.com/fabiomarotti/Annotations/blob/main/Git/GitFlow/img/img_trunk_pick.png"  width="1024" height="" />
<div align="center"> *Figura* 2: Trunk Based Development </div>
<br />
