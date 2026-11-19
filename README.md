# Site da Jungle Degree

Site institucional estático (HTML + CSS puro, sem build nem dependências), bilíngue:
inglês na raiz, português de Portugal em `/pt/`. Responsável: JUNGLE DEGREE, LDA.

## Estrutura

| URL | Ficheiro |
|---|---|
| `/` e `/pt/` | `index.html`, `pt/index.html` (início) |
| `/wild-pack/` e `/pt/wild-pack/` | página do jogo |
| `/wild-pack/privacy/` (EN) e `/wild-pack/privacy/pt/` (PT) | política de privacidade (HTML nativo) |
| `404.html`, `robots.txt`, `favicon.ico`, `assets/` | resto |

`_src/` guarda os rascunhos antigos da política e `logo-source.png` o logótipo original
(ambos excluídos da publicação por `_config.yml`).

## Como editar

Abra os `index.html` e edite o texto. Os caminhos são relativos, por isso o site funciona
igual na raiz de um domínio ou num endereço `utilizador.github.io/repositório/` (exceto o
`404.html`, que usa caminhos absolutos e só fica certo com domínio próprio na raiz).
Ver localmente: `python -m http.server 8000` nesta pasta e abrir <http://localhost:8000>.
Ao mudar a política, altere a data e acrescente uma linha ao histórico de versões, nas duas línguas.

### Novo jogo

Convenção: `/<jogo>/` (página), `/<jogo>/privacy/` (EN), `/<jogo>/privacy/pt/` (PT) e
`/pt/<jogo>/`. Copie a pasta `wild-pack/` (e `pt/wild-pack/`), adapte, e acrescente um cartão
em "Jogos" nos dois `index.html` iniciais.

## Publicar no GitHub Pages (ainda não executado)

Repositório previsto: `pesconi-jd/jungledegree-site` (**público**: o plano gratuito só serve Pages de repositórios públicos). O `origin` já está configurado localmente; falta o push.

1. Criar o repositório vazio no GitHub (sem README nem licença) e só então: `git push -u origin main`.
2. Settings > Pages > Source: **Deploy from a branch**, branch `main`, pasta `/ (root)`.
3. O ficheiro `CNAME` (`jungledegree.com`) já está no repositório; em Pages > Custom domain confirmar `jungledegree.com`.
4. Esperar alguns minutos, ativar **Enforce HTTPS** quando disponível e abrir a política em janela anónima.

## DNS do domínio jungledegree.com na Squarespace (a configurar pelo utilizador)

- Registos `A` para o apex (`@`): `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153` (opcionalmente `AAAA` do GitHub).
- `CNAME` para `www` apontando para `pesconi-jd.github.io`.
- Confirmar os valores na documentação atual do GitHub Pages. Remover registos `A`/`CNAME` antigos que conflitem.

## Endereços absolutos

Canonical, `og:url`, `og:image`, `hreflang`, `sitemap.xml` e `robots.txt` usam `https://jungledegree.com/`. Se o domínio mudar, alterar esses ficheiros e o `CNAME`.
