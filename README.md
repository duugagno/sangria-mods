# sangria-mods

Repositorio de conteudo do **Sangria Falls Launcher**. Guarda o catalogo de mods,
as noticias do painel e as imagens. Os binarios (DLLs e o zip do BepInEx) sao
distribuidos como **release assets**, nao ficam no git.

## Arquivos

- `manifest.json` — catalogo de mods + versao do BepInEx (o launcher le isto)
- `news.json` — noticias do carrossel do painel
- `news/` — imagens das noticias (jpg/png)

## Atualizar um mod

1. Suba a DLL nova como asset de um release (tag `mod-id-x.y.z`).
2. Gere o hash: `Get-FileHash arquivo.dll -Algorithm SHA256`.
3. No `manifest.json`, atualize `versao`, `url` e `sha256` do mod.
4. `git commit` + `git push`. O launcher baixa o diff sozinho.

## Adicionar uma noticia

Edite `news.json` (campos: `tag`, `titulo`, `texto`, `imagem`, `url`) e faca push.
`imagem` e `url` sao opcionais. Imagens podem ficar em `news/` e ser referenciadas
por URL raw, ou apontar para qualquer https.
