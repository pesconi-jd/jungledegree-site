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

## Publicar no GitHub Pages (não executado)

1. Criar um repositório **público** (o plano gratuito só serve Pages de repositórios públicos).
2. `git remote add origin <url>` e `git push -u origin main`.
3. No GitHub: Settings > Pages > Source: **Deploy from a branch**, branch `main`, pasta `/ (root)`.
4. Esperar alguns minutos e abrir o endereço indicado; confirmar a política em modo anónimo.

## Ligar o domínio jungledegree.com (não executado)

1. Escolher o endereço (por exemplo `jungledegree.com` ou `www.jungledegree.com`).
2. No fornecedor de DNS: para o apex, registos `A` para `185.199.108.153`, `185.199.109.153`,
   `185.199.110.153`, `185.199.111.153` (e opcionalmente `AAAA`); para `www`, um `CNAME`
   para `<conta>.github.io`. Confirmar os valores na documentação atual do GitHub Pages.
3. Em Settings > Pages > Custom domain, indicar o domínio (o GitHub cria o ficheiro `CNAME`) e
   ativar **Enforce HTTPS** quando disponível.
4. Depois, acrescentar `sitemap.xml` e a linha `Sitemap:` ao `robots.txt` com o domínio final.
