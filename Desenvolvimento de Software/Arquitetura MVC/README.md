# Arquitetura MVC
- `Model` : BD, file (XML/txt) 
  - `Entity` : Bean, POJO
  - `DAO` : conexão, CRUD
  - `Service` : um serviço para cada entidade ou dao
- `View` : SWING, AWT, SWT, JSF, HTML
- `Controller` : (View , Controller)

# Informações
- `Model`
  - contém a conexão com o banco de dados, ou forma de acesso aos dados.
  - contém a lógica da aplicação, as regras e operações de negócio.
  - processa os dados obtidos do usuário para a forma necessaria que outras camadas logicas possam acessar.
  - representa a informação (dados), regras SQL
  - realiza os CRUD
  - opera dados para o `controller` e não recebe dados da `View`
  
- `View`
  - interação com o usuário
  - proporciona entrada de dados e visualização de respostas para o usuário
  - possui componentes para a entrada e saída de dados
  - a **view** deve refletir o estado do **model**
  
- `Controller`
  - intermedia a camada `Model`e `View`
  - define o comportamento da aplicação
  - interpleta as solicitações (cliques)
  - controla e mapeia as ações


## fluxo de dados
- `User`        ->  `controller` : Usuário clicar, passar dados para controller
- `controller`  ->  `model`      : controller envia dados para model processar 
- `model`       ->  `view`       : model fornece dados processados para a view por meio do controller
- `view`        ->  `User`       : atualiza seu estado para o usuaário




