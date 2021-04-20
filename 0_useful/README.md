# Useful (Proveitoso)

# Sistema de Caminho de Pastas
- URI (Uniform Resource Identifier) [ver +](https://pt.wikipedia.org/wiki/URI)
- RFC 3986 [ver +](https://tools.ietf.org/html/rfc3986)
- [discução sobre](https://pt.stackoverflow.com/questions/198422/caminho-para-acesso-de-pastas-html-css-php-etc)

1. Se o caminho começar com `../` ou `./` então eles serão removidos do prefixo:
`../a/b/c` → `a/b/c`

2. Se o caminho começar com `/./` , `/../` eles serão trocado por `/`
`/./a/b/c` → `/a/b/c`

3. Se terminar com `/.` , `/./` , `/..` irá remover o próprio `/.` e `/..`
`/a/b/c/..` → `/a/b/c/` e `/a/b/c/.` → `/a/b/c/`

4. Se terminar com `/./` e `/../` irá remover um item:
`/a/b/c/../` → `/a/b/`

5. Se `/../` estiver no meio irá remover o prefixo (semelhante a explicação 4):
`/a/b/../c/` → `/a/c/`

6. Se `./` estiver no meio terá o mesmo comportamento que a explicação 2:
`/a/b/./c/` → `/a/b/c/`
