# Desenvolvimento de Software

## Ciclo de vida

- Requerimento
- Planejamento
- Arquitetura e Design do SW
- Desenvolvimento do SW
- Testes
- Implantação do SW (Deploy)

## Modelos
- Modelo Agil
- Modelo Espiral
- Modelo Cascata

# Deploy

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
