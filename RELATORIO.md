# Relatório: site da Jungle Degree (local, nada publicado)

## Feito
Site estático em HTML/CSS puro: início, página do Wild Pack e política de privacidade em EN
(`/wild-pack/privacy/`) e PT-PT (`/wild-pack/privacy/pt/`), com troca de idioma em todas as
páginas, `404.html`, `robots.txt`, favicon/ícones derivados do logótipo, `README.md`.
Testado num servidor local: 0 ligações internas ou âncoras partidas nas 7 páginas, sem
scroll horizontal a 375 px, desktop e telemóvel verificados visualmente.
`CNAME` não criado. Nada de remoto, push ou DNS.

## Conferência da política contra o jogo (leitura apenas)
Confirmado em `declaracoes.md`, `RewardedAdService.cs` e SISTEMA.md 7.30/7.35: sem contas,
servidor próprio, analytics ou compras; save local (nível, moedas, skins, nome, som, vibração);
AdMob + UMP, anúncio premiado opcional só após `CanRequestAds`; 13+, PG, sem tag infantil;
sem permissões de câmara/microfone/localização/armazenamento.

## Pendências para o utilizador
1. **Email de contacto**: usei `pesconi@jungledegree.com` (o texto recebido trazia um "@"
   de largura total, normalizado para ASCII). O jogo, a ficha e as declarações usavam
   `jungledegreelda@gmail.com`. Confirmar que a caixa existe e atualizar o Play Console.
2. **Morada**: confirmar "Rua Fernando Namora, 10, 3.º Dto., 2675-487 Odivelas" (corrigida de
   "namora").
3. **Fontes Rubik e DM Sans**: não incluídas, para não haver pedidos à Google nem descarregar
   ficheiros sem autorização; o CSS usa-as se instaladas, senão fontes do sistema. Para as
   ter, autorizar descarregar os ficheiros (licença OFL) e colocá-los em `assets/fonts/`.
4. **Data de vigência (19/11/2026) e histórico**: a v1.0 (17/11/2026, Google Sites) e a v2.0
   são deduzidas dos documentos; ajustar à data real de publicação.
5. **Revisão jurídica** do texto RGPD: fundamento de licitude (consentimento), prazo de um
   mês, CNPD, transferências (descritas "segundo a Google"; o jogo não faz transferências
   próprias), ausência de encarregado de proteção de dados (não referido; confirmar se há).
6. **Dados vistos pela empresa no AdMob**: o texto diz que não conservamos dados pessoais;
   os relatórios do AdMob são agregados, mas isso não consta do código. Confirmar.
7. **Lista do SDK** (Data safety): conferir o que o AdMob declara na página da Google antes
   de fechar o Console (já pendente em `declaracoes.md`).
8. **Menção a GitHub Pages** na secção "Este sítio web": se mudar de alojamento, atualizar.
9. **Domínio e `CNAME`**; depois `sitemap.xml`, `<link rel="canonical">` e URL absoluta nas
   meta tags `og:image`.
10. **Jogo**: trocar `PrivacyPolicyLink.Url` e o campo do Play Console pela URL nova (outra
    sessão). A Play verifica a página: ela é HTML nativo e sem cookies.
11. Link da Google Play no site: a página diz "Em breve"; trocar pelo endereço da ficha quando existir.
