# Desenvolvimento de Software

## Ciclo de vida

- Requerimento
- Planejamento
- Arquitetura e Design do SW
- Desenvolvimento do SW
- Testes
- Implantação do SW (Deploy)

## Metodologias Ágeis
- XP (eXtreme Programming)
- Scrum
- Kanban
- FDD (Feature Driven Development)
- MSF (Microsoft Solutions Framework)
- Modelo Espiral
- Modelo Cascata


## CI / CD / CD

- **CI** - Continuous Integration (Integração Contínua)
  - Build
  - Test
  - Merge (merge day)

- **CD** - Continuous Delivery (Entrega Contínua)
  - Automaticaly Release To Repository
  - Garantir estar sempre pronto para implantação em um ambiente de produção.

- **CD** - Continuous Deployment (Implantação Contínua)
  - Automaticaly Deploy to Production
  - Etapa final de uma pipeline CI/CD
  

## DevOps (Development and Operations)
> --> Plan >> Code >> Build >> Test >> Release >> Deploy >> Operate >> Monitor --> 

- Desenvolvedores de Software
  - Plan : (Openstack)
  - Code : (Git, GitLab, Jira)
  - Build : (Gradle, Sonatype Nexus, Maven, sbt)
  - Test : (Azure, JUnit)
- Operadores de Software
  - Release : (Jekins, CodeShip)  
  - Deploy : (AWS, Docker, DC/OS)
  - Operate : (Chef, Ansible, Kubernetes)
  - Monitor : (Grafana, Graylog, DataDog, Nagios, splunk)

## Deploy

## Estratégias de Deploy
- Rolling
> O Deploy é realizado gradualmente. <br>
> Versão Antiga e Nova coexistem ate uma versão estavel.

- Blue-Green
> Blue: versão ativa/atual/estavel, recebe requerimentos <br>
> Green: versão teste/nova, apos estabilizar, começa a recer o requerimentos do Blue. (ver Jekins, AWS, servidores imutáveis) <br>
> Mirror: dois ambientes identicos. <br>
> Load Balancer: direcionamento de trafego para o ambiente desejado. <br>
> Realizar testes e atualizações em tempo de produção

- Canary
> Versão nova disponivel para uma parcela de usuários <br>
> Acompanha o interesse e reações do publico antes de liberar acesso total.<br>


## Ambientes de Deploy
- VPS (configurar ambiente)
- PaaS (Platform as a Service)
  - Heroku

## [XP](https://pt.wikipedia.org/wiki/Programa%C3%A7%C3%A3o_extrema)
