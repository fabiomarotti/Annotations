# Nomenclaturas (Convensão)

> Exemplo: <br>
>  google-maps-devops-1.0.0-ALPHA3 <br>
> {{empresa}} - {{projeto}} - {{ **tipo** }} - {{ **versão** }}

- **tipo**: front, back, web-service, devops
- **versão**: {{ * }} . {{ * }} . {{ * }} - {{ Qualificador }} {{ Build }}

| Versão                                            | *         | *         | *         | Qualificador | Build |
|---                                                |---        |---        |---        |---           |       |
|Característica	                                    |Maior	    |Menor	    |Micro  	  | a , b , rc   |       | 
|Escopo	                                            |Inovação	  |Evolução	  |Manutenção	|              |       |
|Bug                                                |	          |           | X	        |              |       |
|Improvement			                                  |           |           | X         |	             |       |
|Feature Request	                                  | X	        | X         |           |              |       |		
|Pode haver Depreciação?	                          | Sim       | Sim       | Não       |	             |       |
|Pode haver Retirada?	                              | Sim       | Não       | Não       |              |       |	
|Periodicidade Mínima	                              | Planejada	| Planejada	| Imediata	|              |       |
|Periodicidade Máxima	                              | Planejada	| Semestral	| Mensal    |              |       |

- Qualificador : Snapshot 
  - a : ALPHA 
  - b : BETA 
  - rc : Relase Candidate
- Numero de Build

## Commits

- `build`: Mudanças que afetam o sistema de build ou dependências externas (example scopes: gulp, broccoli, npm);
- `ci`: Mudanças nos arquivos/scripts de continuos integration (example scopes: Travis, Circle, BrowserStack, SauceLabs);
- `docs`: Mudanças na documentação;
- `feat`: Nova “feature”;
- `fix`: Correção de um bug;
- `perf`: Mudança que melhora performance;
- `refactor`: Mudança no código que não adiciona novas “features” ou corrige bugs;
- `style`: Mudanças que não afetam o significado do código (white-space, formatting, missing semi-colons, etc);
- `test`: Adicionando testes faltantes ou corrigindo testes existentes.

# Liberação de Software
- Desenvolvimento
  - Pre-Alfa
  - Alfa
  - Beta
  - Release Candidate
- Lançamento
  - RTM
  - GA

[ver +](https://pt.wikipedia.org/wiki/Ciclo_de_vida_de_libera%C3%A7%C3%A3o_de_software)

# Referências
- [Gui Basico GitHub](https://medium.com/enext-ideas/convens%C3%A3o-de-nomenclatura-no-bitbucket-github-dad1acb0b026)
- [Semantic Version](https://semver.org/)
- [Convensão de Commits](https://www.conventionalcommits.org/en/v1.0.0/#summary)
