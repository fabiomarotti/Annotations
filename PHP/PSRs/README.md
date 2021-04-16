# PSRs

Existem 16 PSRs desenvolvidas/em desenvolvimento pela [PHP-FIG](https://www.php-fig.org/) (Framework Interoperability Group).
As PSRs aceitas são:

- `Basic Coding Standard` (Padrão de codificação básica)
Aborda os elementos que devem ser considerados para garantir um código de de alta interoperabilidade.

- `Coding Style Guide` (Guia de estilo de codificação)
Aborda como deve ser feita a formatação para facilitar a leitura do código por outros desenvolvedores.

- `Logger Interface` (Interface de Logger)
Descreve uma interface comum para bibliotecas de Log é bem útil para quem precisa de uma arquitetura de log mais universal.

- `Autoloading Standard` (Padrão de auto-carregamento)
Descreve uma especificação para auto-carregamento de classes pelo diretório do arquivo. Também diz onde colocar arquivos que serão auto-carregados. Se você não quer ficar dando include/require nos seus projetos PHP, vale bastante a pena dar uma olhada.

- `Caching Interface` (Interface de Cache)
Descreve uma interface padrão para desenvolver sistemas de Cache ou implementar uma arquitetura de cache mais robusta no seu sistema.

- `HTTP Message Interface` (Interface de Mensagem HTTP)
Descreve uma interface padrão para desenvolvimento de mensagens HTTP. Muito útil para quem vai montar uma API do zero.

- `Container Interface` (Interface para Containers)
Descreve uma interface padrão para desenvolvimento de Containers para injeção de dependência. É extremamente importante para entender como os frameworks realizam certas "magias" ou criar seu próprio framework MVC.

- `Hypermedia Links` (Links serializados)
Descreve uma interface simples para representação de links, independente da forma de serialização. Isso é muito bom para quem constrói APIs (ou endpoints soltos) e precisa passar tags ou links serializados na resposta do servidor pra aplicação sem se matar com escape de strings.

- `HTTP Handlers` (Gerenciadores de requisição HTTP)
Muito importante pra quem quer entender como um middlewares ou controllers devem funcionar.

- `Simple Cache` (Interface de cache simples)
Caso você tenha achado a PSR de Caching muito complexa ou muito over kill pro seu problema, você pode tentar a abordagem mais simples. Ambas as PSRs são independentes e compatíveis entre sí.

- `HTTP Factories` (Fábricas de requisições e respostas)
Diretamente relacionado ao HTTP Handlers, descreve uma interface para construção dos Requests/Responses

- `HTTP Client` (Consumidor de requisições e respostas)
Também diretamente relacionada ao HTTP Handlers, descreve uma interface para envio das Requests/Responses!

