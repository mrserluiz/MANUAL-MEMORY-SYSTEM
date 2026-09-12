# MEMÓRIA DO PROJETO — EXBR SITE

**ID da memória:** `#EXBR_Site`  
**Arquivo:** `memories/EXBR_Site.md`  
**Criado em:** 06/09/2026  
**Última atualização:** 12/09/2026  
**Status geral:** EM DESENVOLVIMENTO

---

# Identidade do Projeto

**Nome do projeto:** EXBR Site  
**Organização / Outfit:** EXBR  
**Jogo:** PlanetSide 2  
**Tipo:** Site institucional e comunitário  
**Idioma principal:** Português do Brasil  
**Público principal:** Membros atuais, novos jogadores e interessados em conhecer a Outfit EXBR.

---

# Repositórios Oficiais

## Site EXBR

```text
https://github.com/EXBRClub/Home-page
```

Este repositório será a **fonte de verdade técnica** do site EXBR.

## Site usado como referência estrutural

```text
https://github.com/mrserluiz/EtherCraft
```

O EtherCraft serve como referência de:

- organização modular;
- compatibilidade com GitHub Pages;
- separação entre HTML, CSS, JavaScript, dados e recursos;
- componentes reutilizáveis;
- responsividade;
- SEO;
- facilidade de manutenção.

O EXBR Site deverá possuir identidade visual própria. A referência ao EtherCraft é estrutural e não significa copiar sua temática medieval, cores ou conteúdo.

## Sistema de memória

```text
https://github.com/mrserluiz/MANUAL-MEMORY-SYSTEM
```

Esta memória é cumulativa. Atualizações futuras devem acrescentar histórico e preservar decisões anteriores, salvo quando o usuário ordenar explicitamente uma substituição.

---

# Objetivo Principal

Criar a página oficial da Outfit EXBR para PlanetSide 2.

O site funcionará como uma janela de divulgação da comunidade, apresentando sua identidade, atividades, organização e formas de ingresso.

Objetivos previstos:

- apresentar a EXBR;
- divulgar a Outfit para jogadores de PlanetSide 2;
- reunir informações úteis para membros;
- apresentar operações, eventos e atividades;
- facilitar o recrutamento;
- direcionar visitantes para os canais oficiais da comunidade;
- construir uma presença digital própria para a EXBR.

---

# Conceito Visual

## CONFIRMADO

A identidade visual será inspirada em uma interface militar futurista espacial, coerente com o universo de PlanetSide 2.

Direção aprovada:

- ambiente de guerra futurista espacial;
- menus modernos;
- painéis semitransparentes;
- aparência semelhante a uma interface tática;
- linhas, recortes e detalhes de HUD;
- sensação de central de operações;
- alto contraste e leitura clara;
- experiência responsiva para computador e celular;
- visual próprio da EXBR, sem reutilizar a temática medieval do EtherCraft.

## DIREÇÃO VISUAL INICIAL

Elementos previstos:

- fundo escuro com profundidade;
- superfícies translúcidas com desfoque;
- bordas finas e luminosas;
- detalhes geométricos;
- tipografia forte e técnica;
- animações discretas;
- indicadores visuais inspirados em sistemas militares;
- navegação semelhante a um painel de comando;
- efeitos de luz controlados, sem comprometer a legibilidade.

## NÃO DEFINIDO

Ainda não foram confirmados:

- logotipo oficial;
- paleta oficial da EXBR;
- facção principal;
- servidor de PlanetSide 2;
- plataforma;
- imagens oficiais;
- vídeos;
- endereço do Discord;
- redes sociais;
- slogan;
- textos institucionais definitivos.

Essas informações não devem ser inventadas.

---

# Arquitetura Técnica

## CONFIRMADO

O projeto será:

- estático;
- compatível com GitHub Pages;
- desenvolvido em HTML, CSS e JavaScript;
- mobile-first;
- modular;
- sem dependência obrigatória de frameworks;
- organizado para permitir expansão futura.

## Estrutura Base Planejada

```text
Home-page/
│
├── index.html
├── README.md
├── MAPA-SITE.txt
│
├── pages/
│   ├── sobre.html
│   ├── recrutamento.html
│   ├── operacoes.html
│   └── comunidade.html
│
├── assets/
│   ├── images/
│   │   ├── logo/
│   │   ├── backgrounds/
│   │   ├── operacoes/
│   │   └── members/
│   ├── icons/
│   └── fonts/
│
├── css/
│   ├── reset.css
│   ├── base.css
│   ├── components.css
│   └── pages/
│       ├── home.css
│       ├── sobre.css
│       ├── recrutamento.css
│       ├── operacoes.css
│       └── comunidade.css
│
├── js/
│   ├── main.js
│   └── modules/
│
└── data/
    ├── operacoes.json
    └── membros.json
```

## Estado da Estrutura

A estrutura acima está **PLANEJADA** e ainda não deve ser tratada como totalmente implementada.

As páginas, diretórios e arquivos somente passam a ser **CONFIRMADOS** depois de existirem no repositório oficial.

---

# CSS Modular

## DECISÃO CONFIRMADA

A organização seguirá o padrão estrutural já adotado no EtherCraft:

### `css/reset.css`

Normalização dos estilos do navegador.

### `css/base.css`

Responsável por:

- variáveis de cor;
- tipografia;
- fundo global;
- containers;
- espaçamentos;
- transições;
- tokens visuais;
- configuração geral de acessibilidade.

### `css/components.css`

Responsável por componentes reutilizáveis:

- cabeçalho;
- navegação;
- botões;
- cards;
- painéis;
- etiquetas;
- indicadores;
- rodapé.

### `css/pages/*.css`

Responsável apenas pelo visual específico de cada página.

---

# Navegação Inicial

## PLANEJADO

Menu principal previsto:

- Início;
- Sobre a EXBR;
- Recrutamento;
- Operações;
- Comunidade.

Os nomes e destinos poderão ser ajustados conforme o conteúdo oficial for definido.

---

# Home

## PLANEJADO

A página inicial deverá apresentar a EXBR de forma imediata.

Blocos previstos:

1. identificação da EXBR;
2. apresentação como Outfit de PlanetSide 2;
3. chamada para conhecer a comunidade;
4. resumo institucional;
5. áreas de atuação da Outfit;
6. destaque para recrutamento;
7. acesso aos canais oficiais.

A primeira tela deverá transmitir a sensação de uma central de comando futurista, sem esconder a informação principal atrás de excesso de efeitos.

---

# Páginas Internas

## PLANEJADO

### Sobre a EXBR

Apresentação da história, identidade, objetivos e estilo de jogo da Outfit.

### Recrutamento

Informações para novos membros, requisitos, processo de entrada e canal oficial de contato.

### Operações

Espaço para divulgar operações, eventos, treinamentos e registros de atividades.

### Comunidade

Área para canais oficiais, convivência, membros e informações comunitárias.

---

# Dados e Conteúdo Dinâmico

## PLANEJADO

Arquivos JSON poderão ser utilizados para conteúdo que precise de manutenção frequente, como:

- operações;
- eventos;
- membros;
- destaques;
- registros históricos.

## NÃO IMPLEMENTADO

Não existe ainda:

- banco de dados;
- autenticação;
- painel administrativo;
- sistema de cadastro;
- integração com API de PlanetSide 2;
- integração com Discord;
- conteúdo atualizado automaticamente.

Esses recursos somente deverão ser adicionados quando forem solicitados e definidos.

---

# GitHub Pages

## CONFIRMADO COMO REQUISITO

Todos os caminhos devem funcionar dentro do projeto hospedado pelo GitHub Pages.

Endereço esperado:

```text
https://exbrclub.github.io/Home-page/
```

Caminhos internos deverão ser relativos ao nível do arquivo.

Exemplos:

Na raiz:

```text
pages/sobre.html
assets/images/logo/
css/base.css
```

Dentro de `pages/`:

```text
../index.html
../assets/images/
../css/base.css
```

Não usar caminhos iniciados apenas por `/`, porque podem ignorar o prefixo `/Home-page/`.

---

# SEO e Acessibilidade

## PLANEJADO

O site deverá incluir:

- idioma `pt-BR`;
- título e descrição próprios em cada página;
- marcação semântica;
- navegação por teclado;
- foco visível;
- contraste adequado;
- textos alternativos para imagens;
- layout responsivo;
- metadados para mecanismos de busca;
- URL canônica correta;
- respeito a `prefers-reduced-motion`.

Metadados sociais com imagem somente deverão ser configurados quando existir uma imagem oficial aprovada.

---

# Regras de Continuidade

1. O repositório `EXBRClub/Home-page` é a fonte de verdade técnica do site.
2. Antes de grandes alterações, verificar os arquivos existentes no GitHub.
3. Não substituir funcionalidades funcionando sem necessidade.
4. O EtherCraft deve ser usado como referência estrutural, não como identidade visual.
5. Não copiar conteúdo, credenciais, Firebase ou sistemas específicos do EtherCraft para o EXBR Site.
6. Não inventar informações oficiais da Outfit.
7. Preservar compatibilidade com GitHub Pages.
8. Manter HTML, CSS, JavaScript, dados e recursos organizados de forma modular.
9. Diferenciar claramente `CONFIRMADO`, `EM DESENVOLVIMENTO`, `PLANEJADO` e `NÃO IMPLEMENTADO`.
10. A memória é cumulativa.
11. Updates futuros devem acrescentar histórico em vez de apagar decisões anteriores.
12. Todo update importante deve terminar com o mapa atualizado do site.
13. Relatórios UPDATE solicitados pelo usuário devem ser entregues em formato pronto para copiar e colar.

---

# Estado Atual — 06/09/2026

## CONFIRMADO

- Projeto definido como site da Outfit EXBR.
- Jogo principal definido como PlanetSide 2.
- Repositório oficial definido: `EXBRClub/Home-page`.
- EtherCraft definido como referência estrutural.
- GitHub Pages definido como plataforma alvo.
- Arquitetura modular aprovada.
- Conceito visual futurista espacial aprovado.
- Menus modernos e semitransparentes aprovados.
- Público principal definido como membros e interessados na Outfit.

## EM DESENVOLVIMENTO

- planejamento da Home;
- identidade visual inicial;
- definição da arquitetura de páginas;
- criação da base técnica.

## PLANEJADO

- Home institucional;
- páginas Sobre, Recrutamento, Operações e Comunidade;
- CSS modular;
- JavaScript global;
- estrutura de dados;
- recursos visuais oficiais;
- SEO e acessibilidade;
- publicação pelo GitHub Pages.

## NÃO IMPLEMENTADO

- arquivos iniciais do site no repositório;
- logotipo e ícones oficiais;
- conteúdo institucional definitivo;
- links oficiais;
- integrações;
- banco de dados;
- autenticação;
- painel administrativo.

## BLOQUEIO ATUAL

Na criação desta memória, a conexão GitHub disponível pela conta `mrserluiz` possuía leitura no repositório `EXBRClub/Home-page`, mas não possuía permissão de escrita.

O repositório continha somente:

```text
LICENSE
```

A implementação inicial do site depende de conceder à conta conectada permissão de escrita nesse repositório ou conectar uma conta autorizada.

---

# Próximo Passo

Liberar escrita no repositório `EXBRClub/Home-page` e então criar a primeira versão funcional da Home, mantendo a estrutura modular definida nesta memória.

---

# Mapa Atual do Site

## CONFIRMADO NO REPOSITÓRIO

```text
Home-page/
└── LICENSE
```

## ESTRUTURA PLANEJADA

```text
Home-page/
├── LICENSE
├── index.html
├── README.md
├── MAPA-SITE.txt
├── pages/
├── assets/
├── css/
├── js/
└── data/
```


---

# UPDATE — 06/09/2026 — Permissão do repositório

## CONFIRMADO

- A conta `mrserluiz` foi adicionada como colaboradora de `EXBRClub/Home-page`.
- O GitHub passou a indicar permissão `push` para a conta.
- A primeira versão da Home foi preparada com HTML, CSS modular e JavaScript.
- A base preparada utiliza interface tática futurista, painéis semitransparentes, navegação responsiva e seções Início, Sobre, Operações, Recrutamento e Comunidade.

## NÃO IMPLEMENTADO NO REPOSITÓRIO

Os arquivos ainda não foram gravados em `EXBRClub/Home-page`.

A instalação do aplicativo GitHub disponível nesta sessão pertence somente à conta `mrserluiz`. O GitHub recusou operações de gravação no repositório pertencente à conta `EXBRClub` com o retorno `Resource not accessible by integration`.

## BLOQUEIO ATUAL

O aplicativo GitHub precisa ser instalado ou conectado pela conta proprietária `EXBRClub`, com acesso ao repositório `Home-page`.

Conceder colaboração à conta `mrserluiz` não autoriza automaticamente a instalação do aplicativo vinculada a essa conta a modificar repositórios pertencentes a outro usuário.

## PRÓXIMO PASSO

Conectar a conta `EXBRClub` ao GitHub no ChatGPT e autorizar o repositório `Home-page`. Depois disso, publicar a base preparada e verificar os arquivos diretamente no repositório.

## MAPA ATUAL CONFIRMADO

```text
Home-page/
└── LICENSE
```

## MAPA PREPARADO — AINDA NÃO PUBLICADO

```text
Home-page/
├── LICENSE
├── index.html
├── README.md
├── MAPA-SITE.txt
├── css/
│   ├── reset.css
│   ├── base.css
│   ├── components.css
│   └── pages/
│       └── home.css
└── js/
    └── main.js
```


---

# UPDATE — 06/09/2026 — Fluxo com Repositório Duplo

## OBJETIVO

Permitir que a IA desenvolva e atualize o site diretamente na conta conectada `mrserluiz`, enquanto o usuário replica manualmente os mesmos arquivos no repositório oficial da EXBR.

## DECISÃO CONFIRMADA

O projeto passa a trabalhar com dois repositórios espelhados:

### Desenvolvimento e atualizações pela IA

```text
https://github.com/mrserluiz/Home-page
```

### Repositório oficial da EXBR

```text
https://github.com/EXBRClub/Home-page
```

O usuário fará manualmente a transferência das atualizações do repositório de desenvolvimento para o repositório oficial.

## REGRA DE COMPATIBILIDADE DUPLA

Os dois repositórios devem manter exatamente a mesma estrutura interna.

Exemplo:

```text
mrserluiz/Home-page/index.html
=
EXBRClub/Home-page/index.html
```

Todos os caminhos funcionais do HTML, CSS e JavaScript devem ser relativos.

Exemplos aprovados:

```text
css/base.css
css/pages/home.css
js/main.js
pages/sobre.html
../assets/images/
```

Não utilizar caminhos internos iniciados somente por `/`, porque eles podem ignorar o diretório `/Home-page/` no GitHub Pages.

URLs externas absolutas são permitidas quando necessárias.

A URL canônica e os metadados públicos devem apontar para o endereço oficial:

```text
https://exbrclub.github.io/Home-page/
```

## BLOQUEIO ANTERIOR

**STATUS:** RESOLVIDO POR NOVO FLUXO

A integração não conseguia gravar diretamente em `EXBRClub/Home-page`, mesmo com `mrserluiz` como colaborador.

A solução adotada foi criar o repositório de desenvolvimento `mrserluiz/Home-page` e manter a atualização do repositório oficial sob responsabilidade manual do usuário.

## IMPLEMENTADO

A primeira versão funcional do site foi criada em:

```text
https://github.com/mrserluiz/Home-page
```

Commit principal:

```text
54bd3bf1572d36b0f50c7617e5e21244d128ec9a
```

## CONTEÚDO IMPLEMENTADO

- Home responsiva de página única.
- Identidade visual militar futurista espacial.
- Interface inspirada em painel tático.
- Menus e painéis semitransparentes.
- Navegação fixa e responsiva.
- Menu mobile acessível.
- Seções Início, Sobre, Operações, Recrutamento e Comunidade.
- Navegação ativa conforme a rolagem.
- Animações discretas de entrada.
- Respeito a `prefers-reduced-motion`.
- SEO básico.
- URL canônica oficial da EXBR.
- Caminhos relativos compatíveis com os dois repositórios.
- README com instruções do fluxo duplo.
- Mapa estrutural do site.

## NÃO IMPLEMENTADO

- logotipo oficial;
- imagens oficiais;
- facção e servidor;
- plataforma;
- Discord;
- redes sociais;
- conteúdo histórico definitivo;
- agenda real de operações;
- formulário ou canal definitivo de recrutamento;
- páginas internas independentes;
- banco de dados;
- autenticação;
- integrações externas.

Essas informações não devem ser inventadas.

## PRÓXIMO PASSO

O usuário deve copiar a estrutura de `mrserluiz/Home-page` para `EXBRClub/Home-page`.

Depois, confirmar os dados oficiais da Outfit para substituir os conteúdos provisórios e expandir o portal.

## MAPA ATUAL DO REPOSITÓRIO DE DESENVOLVIMENTO

```text
Home-page/
├── index.html
├── README.md
├── MAPA-SITE.txt
├── css/
│   ├── reset.css
│   ├── base.css
│   ├── components.css
│   └── pages/
│       └── home.css
└── js/
    └── main.js
```

## MAPA ESPERADO NO REPOSITÓRIO OFICIAL

```text
Home-page/
├── LICENSE
├── index.html
├── README.md
├── MAPA-SITE.txt
├── css/
│   ├── reset.css
│   ├── base.css
│   ├── components.css
│   └── pages/
│       └── home.css
└── js/
    └── main.js
```


---

# UPDATE — 06/09/2026 — Página de Login

## DECISÃO CONFIRMADA

Ao clicar em `LOGIN`, o visitante deve acessar uma página própria de login.

## IMPLEMENTADO NO REPOSITÓRIO DE DESENVOLVIMENTO

Repositório:

```text
https://github.com/mrserluiz/Home-page
```

Commit:

```text
9ca7ebd7ff796be690e1e272ef20b0300b4f9837
```

Alterações realizadas:

- identidade do cabeçalho atualizada para `EXÉRCITO BRASILEIRO`;
- link verde `LOGIN` posicionado abaixo de `COMUNIDADE`;
- página `pages/login.html` criada;
- estilo modular `css/pages/login.css` criado;
- navegação e caminhos mantidos relativos para funcionar nos dois repositórios;
- README e mapa do site atualizados.

## ESTADO DA AUTENTICAÇÃO

**INTERFACE IMPLEMENTADA / AUTENTICAÇÃO NÃO IMPLEMENTADA**

A página possui formulário visual com campos bloqueados e informa que o acesso está em configuração. Nenhuma credencial é enviada ou armazenada.

A autenticação real dependerá da definição de um serviço seguro, regras de cadastro e fonte autorizada de membros.

## FLUXO DUPLO MANTIDO

O usuário deve copiar manualmente as mesmas alterações para:

```text
https://github.com/EXBRClub/Home-page
```

A estrutura e os caminhos internos são compatíveis com ambos os repositórios.

## MAPA ATUAL DO REPOSITÓRIO DE DESENVOLVIMENTO

```text
Home-page/
├── index.html
├── README.md
├── MAPA-SITE.txt
├── pages/
│   └── login.html
├── css/
│   ├── reset.css
│   ├── base.css
│   ├── components.css
│   └── pages/
│       ├── home.css
│       └── login.css
└── js/
    └── main.js
```


---

# UPDATE — 07/09/2026 — Consolidação do portal, área de membros e Firebase

## OBJETIVO DESTA ETAPA

Transformar a interface demonstrativa de Login e Perfil em uma área funcional de membros, com autenticação por e-mail e senha, persistência no Firestore e separação segura entre usuários padrão e administradores.

## ESTADO DOS REPOSITÓRIOS

O fluxo duplo permanece confirmado:

- desenvolvimento e atualizações pela IA: `mrserluiz/Home-page`;
- repositório oficial: `EXBRClub/Home-page`;
- o usuário mantém os dois repositórios sincronizados manualmente pelo remote duplo;
- todos os caminhos internos continuam relativos e compatíveis com os dois endereços do GitHub Pages.

Commit atual do repositório de desenvolvimento:

`2b68b66b001652e4f35090be0f648511c81dae60` — `feat: integra Firebase Auth e perfis com permissões`.

## INTERFACE E IDENTIDADE — IMPLEMENTADO

- Home responsiva com interface militar futurista espacial.
- Cabeçalho estreito, navegação com iluminação central e Login chanfrado.
- Indicador verde de Portal ativo com pulsação suave.
- Barra tática inferior curva com seis ícones PNG individuais.
- Somente o item selecionado recebe borda e iluminação amarelas e deslocamento vertical.
- Cascata ambiente de pontos, com correção de compatibilidade para Opera GX e fase preservada por guia.
- Efeito inicial de montagem executado apenas na primeira abertura da Home em cada guia.
- Favicon, ícones para celular e manifesto de aplicativo web.
- Cabeçalho, rodapé e espaçamento da marca EXBR corrigidos para celular.
- Discord oficial de recrutamento: `https://discord.gg/CGYwr2uCSu`.

## OPERAÇÕES E ALERTAS — IMPLEMENTADO

- Monitor de alertas integrado à API pública do PS2Alerts.
- Fonte de consulta: `https://ps2alerts.com/alert-history`.
- Connery e Emerald são tratados visualmente como o servidor unificado Osprey.
- Alertas ativos exibem mapa, tempo restante, território e população.
- Sem alerta ativo, o portal informa `SEM ALERTA ATIVO` sem afirmar que o servidor foi desligado.
- O último mapa iniciado registrado pelo PS2Alerts é mantido como referência.
- Falhas da API exibem estado de conexão instável e link para o histórico.

## PERFIL DO MEMBRO — IMPLEMENTADO

- Página protegida `pages/perfil.html`.
- Visitantes sem sessão são redirecionados ao Login.
- Nome, função, patente, avatar, bandeira e medalhas são carregados do Firestore.
- Três templates de soldado: Assalto, Pesado e Reconhecimento.
- Bandeira brasileira animada com tratamentos Brasil, Comando e Noturna.
- Controles de personalização ficam escondidos e abrem pelo botão Editar perfil.
- Medalhas usam emoji temporário e aceitam `iconUrl` para PNG definitivo.
- Hierarquia militar com 17 patentes em `data/patentes.json`.
- Patente inicial confirmada: Soldado.
- Área central do perfil permanece reservada para desenvolvimento futuro.

## FIREBASE — CONFIRMADO E IMPLEMENTADO

Projeto Firebase: `exbr-0709`.

Configuração realizada em 07/09/2026:

- aplicativo Web registrado como `EXBR Portal`;
- Firebase Authentication inicializado;
- provedor E-mail/senha ativado;
- SDK modular Firebase para navegador conectado ao site;
- persistência de sessão ativada no navegador;
- redefinição de senha por e-mail disponível;
- Cloud Firestore conectado ao perfil;
- regras de segurança publicadas e versionadas em `firestore.rules`;
- nenhuma chave de conta de serviço ou credencial privada foi adicionada ao repositório.

Não existe cadastro público no site. Inicialmente, as contas serão criadas pela administração no Firebase Authentication.

No primeiro login, o portal cria automaticamente:

`users/{uid}`

com os campos `email`, `displayName`, `role`, `rankId`, `avatarId`, `bannerId`, `createdAt` e `updatedAt`.

## PAPÉIS E PERMISSÕES — CONFIRMADO

Papéis iniciais:

- `member`: usuário padrão;
- `admin`: administrador.

Todo novo perfil criado pelo site recebe obrigatoriamente:

- `role: member`;
- `rankId: soldado`.

Permissões do membro:

- ler o próprio perfil;
- ler as próprias medalhas;
- alterar somente nome de exibição, avatar e bandeira;
- não pode promover a própria conta;
- não pode alterar função, patente, medalhas ou operações.

Permissões do administrador:

- consultar e editar perfis;
- alterar função e patente;
- criar, editar e excluir operações;
- conceder, editar e remover medalhas.

O primeiro administrador deve ser definido manualmente no Firestore, alterando `users/{uid}.role` para `admin` depois do primeiro login. Depois disso, o painel administrativo futuro poderá assumir essas tarefas.

Estruturas reservadas:

- medalhas: `users/{uid}/medals/{medalId}`;
- operações: `operations/{operationId}`.

## VALIDAÇÃO REALIZADA

- Sintaxe dos módulos JavaScript validada.
- Login publicado no GitHub Pages com campos habilitados.
- Acesso direto ao Perfil sem sessão redireciona corretamente para o Login.
- Provedor E-mail/senha confirmado como ativado no Console Firebase.
- Nova versão das regras confirmada no histórico do Firestore.
- Documentação técnica criada em `FIREBASE.md`.

## NÃO IMPLEMENTADO

- cadastro público;
- painel visual de administração;
- editor de operações;
- interface administrativa para conceder medalhas;
- interface administrativa para alterar patentes e papéis;
- contas iniciais de membros;
- escolha do conteúdo para a área central do perfil.

## PRÓXIMO PASSO

Criar a primeira conta no Firebase Authentication, realizar o primeiro login para gerar `users/{uid}` e promover manualmente esse perfil para `admin`. Em seguida, construir o painel administrativo.

## MAPA ATUAL DO SITE

```text
Home-page/
├── LICENSE
├── index.html
├── README.md
├── MAPA-SITE.txt
├── FIREBASE.md
├── firestore.rules
├── site.webmanifest
├── assets/
│   ├── icons/
│   │   ├── favicon.svg
│   │   ├── apple-touch-icon.png
│   │   ├── icon-192.png
│   │   ├── icon-512.png
│   │   └── dock/
│   │       ├── inicio.png
│   │       ├── sobre.png
│   │       ├── operacoes.png
│   │       ├── recrutamento.png
│   │       ├── comunidade.png
│   │       └── login.png
│   └── profile/
│       ├── avatars/
│       │   ├── assalto.webp
│       │   ├── pesado.webp
│       │   └── reconhecimento.webp
│       └── banners/
│           └── brasil.webp
├── css/
│   ├── reset.css
│   ├── base.css
│   ├── components.css
│   └── pages/
│       ├── home.css
│       ├── login.css
│       └── perfil.css
├── data/
│   └── patentes.json
├── js/
│   ├── firebase-client.js
│   ├── login.js
│   ├── main.js
│   ├── operations.js
│   └── perfil.js
└── pages/
    ├── login.html
    └── perfil.html
```


---

# UPDATE — 07/09/2026 — Cadastro de membros e código temporário

## CORREÇÃO DE DECISÃO

Este update substitui a decisão anterior que dizia que as contas seriam criadas pela administração.

Os membros podem criar suas próprias contas normalmente pelo portal. A administração não precisa cadastrar e-mails nem criar contas de membros.

## IMPLEMENTADO

Commit do repositório de desenvolvimento:

`8a43b5b3b53ff660d23874acb41696a2e562eeef` — `feat: permite cadastro de membros com codigo temporario`.

A página `pages/login.html` agora oferece dois modos:

- Entrar;
- Criar conta.

O cadastro solicita:

- nome de operador;
- e-mail;
- senha e confirmação;
- código de registro em seis campos individuais.

Código temporário desta fase:

`[0][7][0][9][2][2]`

Após o cadastro, o Firebase Authentication cria a conta e o primeiro acesso cria `users/{uid}` com:

- `role: member`;
- `rankId: soldado`.

A administração permanece responsável por atribuir patentes e conceder medalhas. O membro não pode alterar a própria função, patente ou condecorações.

## LIMITAÇÃO DE SEGURANÇA ATUAL

O código `070922` está implementado no JavaScript público do GitHub Pages. Ele funciona como protótipo do fluxo e filtro visual, mas não é um segredo nem uma barreira de segurança definitiva.

A versão definitiva deverá validar códigos únicos em um ambiente confiável, como Cloud Functions ou outro backend, e não no navegador.

## PLANEJADO — NÃO IMPLEMENTADO

- Bot do Discord para gerar códigos únicos de registro;
- códigos com expiração, uso único e vínculo ao usuário do Discord;
- gestão de membros do Discord;
- registro de presença nas operações;
- estudo do funcionamento e das fontes autorizadas do Recursion Tracker;
- futuro complemento da EXBR para coletar eventos permitidos de combate e apresentar estatísticas no site.

Referência futura para investigação:

`https://recursiontracker.com`

Nenhuma integração com Discord ou Recursion Tracker foi implementada nesta etapa.

## MAPA ATUAL DO SITE

```text
Home-page/
├── LICENSE
├── index.html
├── README.md
├── MAPA-SITE.txt
├── FIREBASE.md
├── firestore.rules
├── site.webmanifest
├── assets/
│   ├── icons/
│   │   ├── favicon.svg
│   │   ├── apple-touch-icon.png
│   │   ├── icon-192.png
│   │   ├── icon-512.png
│   │   └── dock/
│   │       ├── inicio.png
│   │       ├── sobre.png
│   │       ├── operacoes.png
│   │       ├── recrutamento.png
│   │       ├── comunidade.png
│   │       └── login.png
│   └── profile/
│       ├── avatars/
│       │   ├── assalto.webp
│       │   ├── pesado.webp
│       │   └── reconhecimento.webp
│       └── banners/
│           └── brasil.webp
├── css/
│   ├── reset.css
│   ├── base.css
│   ├── components.css
│   └── pages/
│       ├── home.css
│       ├── login.css
│       └── perfil.css
├── data/
│   └── patentes.json
├── js/
│   ├── firebase-client.js
│   ├── login.js
│   ├── main.js
│   ├── operations.js
│   └── perfil.js
└── pages/
    ├── login.html
    └── perfil.html
```


---

# UPDATE — 07/09/2026 — Painel administrativo de membros

## OBJETIVO

Implementar a gestão administrativa visual de membros, patentes e medalhas seguindo as referências anotadas pelo usuário, sem inserir as marcações vermelhas no design.

## IMPLEMENTADO

Commit do repositório de desenvolvimento:

`9587b8e2e74dac24218ba06a0f211be8c93d96bf` — `feat: adiciona painel administrativo de membros`.

### Sessão e navegação

- Na Home, o botão `Login` muda automaticamente para `Perfil` quando existe uma sessão Firebase ativa.
- O último botão da barra tática inferior também alterna entre Login e Perfil.
- Na página de membro, o botão superior permanece como `Perfil`.
- A saída da conta foi mantida como ação separada dentro do Perfil e da Área administrativa.

### Perfil do membro

- O botão `Editar perfil` começa oculto.
- O botão só é revelado quando o dono do perfil clica ou usa o teclado sobre o próprio avatar.
- Após 30 segundos sem atividade na área de identidade, os controles são fechados e ocultados novamente.
- Um usuário padrão somente pode abrir o próprio perfil.
- Administradores podem consultar o perfil de outros membros por `pages/perfil.html?uid={uid}`.
- Os controles de avatar e bandeira nunca são mostrados ao administrador quando ele consulta o perfil de outra pessoa.

### Área administrativa

Nova rota protegida:

`pages/admin.html`

Recursos implementados:

- acesso exclusivo para perfis com `role: admin`;
- redirecionamento de membros comuns para o próprio Perfil;
- pesquisa de soldados por nome, e-mail ou patente;
- lista com avatar, nome e patente atual;
- dois cliques ou tecla Enter sobre o registro abrem o perfil do membro;
- seletor com as 17 patentes de `data/patentes.json`;
- salvamento automático da patente no Firestore;
- botão individual `Adicionar medalha`;
- janela de condecorações com pesquisa;
- campos de operação e data;
- adição automática ao selecionar `+`;
- remoção automática ao selecionar `−`;
- atualização direta de `users/{uid}/medals/{medalId}`.

### Catálogo de medalhas

Criado:

`data/medalhas.json`

Catálogo inicial:

- Medalha de Honra;
- Linha de Frente;
- Precisão Tática;
- Irmandade EXBR;
- Operação Osprey;
- Serviço Distinto.

Os emojis continuam temporários. Cada medalha aceita `iconUrl` para futura substituição pelos ícones PNG oficiais.

## SEGURANÇA

As regras existentes do Firestore já protegem esse fluxo:

- somente `admin` pode listar membros;
- somente `admin` pode alterar patentes;
- somente `admin` pode criar ou remover medalhas;
- membros comuns não ganham novas permissões;
- a verificação visual do painel não substitui as regras do Firestore.

Não foi necessário enfraquecer nem alterar `firestore.rules`.

## ARQUIVOS CRIADOS

```text
pages/admin.html
css/pages/admin.css
js/admin.js
js/session-ui.js
data/medalhas.json
```

## ARQUIVOS ATUALIZADOS

```text
index.html
pages/perfil.html
css/pages/perfil.css
js/perfil.js
README.md
FIREBASE.md
MAPA-SITE.txt
```

## NÃO IMPLEMENTADO

- painel de criação e edição do catálogo de tipos de medalha;
- ícones PNG oficiais das medalhas;
- editor administrativo de operações;
- bot do Discord;
- coleta de presença em operações;
- integração com Recursion Tracker.

## MAPA ATUAL DO SITE

```text
Home-page/
├── LICENSE
├── index.html
├── README.md
├── MAPA-SITE.txt
├── FIREBASE.md
├── firestore.rules
├── site.webmanifest
├── assets/
│   ├── icons/
│   │   ├── favicon.svg
│   │   ├── apple-touch-icon.png
│   │   ├── icon-192.png
│   │   ├── icon-512.png
│   │   └── dock/
│   │       ├── inicio.png
│   │       ├── sobre.png
│   │       ├── operacoes.png
│   │       ├── recrutamento.png
│   │       ├── comunidade.png
│   │       └── login.png
│   └── profile/
│       ├── avatars/
│       │   ├── assalto.webp
│       │   ├── pesado.webp
│       │   └── reconhecimento.webp
│       └── banners/
│           └── brasil.webp
├── css/
│   ├── reset.css
│   ├── base.css
│   ├── components.css
│   └── pages/
│       ├── admin.css
│       ├── home.css
│       ├── login.css
│       └── perfil.css
├── data/
│   ├── medalhas.json
│   └── patentes.json
├── js/
│   ├── admin.js
│   ├── firebase-client.js
│   ├── login.js
│   ├── main.js
│   ├── operations.js
│   ├── perfil.js
│   └── session-ui.js
└── pages/
    ├── admin.html
    ├── login.html
    └── perfil.html
```


---

# UPDATE — 07/09/2026 — Refinamento visual do Login

## IMPLEMENTADO

Commit do repositório de desenvolvimento:

`3479a39be5edb52163345b5bd313d296665d5821` — `style: refina indicadores da pagina de acesso`.

Alterações realizadas em `pages/login.html` e `css/pages/login.css`:

- removido completamente o emblema circular `EXBR AUTH` do terminal de identificação;
- o título e o formulário passaram a ocupar naturalmente o espaço liberado;
- indicador `Canal de acesso ativo` alterado do laranja para o verde do Login e do Portal ativo;
- linha lateral, ponto luminoso, fundo e brilho agora usam verde;
- ponto verde recebeu pulsação calma;
- pulsação é desativada quando o usuário utiliza preferência de movimentos reduzidos;
- nenhuma marcação vermelha da imagem de referência foi incluída no design.


---

# UPDATE — 07/09/2026 — Página dedicada de Operações

## OBJETIVO

Criar uma página exclusiva para consultar e participar das operações da EXBR, mantendo simultaneamente o resumo de operações e o monitor do PS2Alerts no setor atual da Home.

## IMPLEMENTADO

Commit do repositório de desenvolvimento:

`56d72eedc233d6300e9625b82543122887eea95c` — `feat: cria pagina dedicada de operacoes`.

### Home e navegação

- O setor `#operacoes` da Home continua existindo.
- A Home carrega até três operações atuais do Firestore e usa `data/operacoes.json` como conteúdo reserva.
- Os cartões não exibem as antigas numerações 01, 02 e 03.
- Cada cartão abre diretamente a operação correspondente em `pages/operacoes.html`.
- As imagens de operação aceitam PNG por caminho relativo ou URL e se deslocam levemente para a direita ao passar o mouse.
- O primeiro uso do atalho inferior de Operações em uma guia leva ao setor da Home.
- Depois que a página dedicada é visitada, o mesmo atalho passa a retornar diretamente para ela enquanto a guia permanecer aberta.

### Página dedicada

Nova rota:

`pages/operacoes.html`

Recursos:

- lista vertical rolável de operações;
- imagem, nome, tipo, descrição, detalhes, data e horário;
- medalha prevista com emoji temporário ou `medalIconUrl` para PNG definitivo;
- botão de participação para membros autenticados;
- redirecionamento ao Login quando o visitante ainda não está autenticado;
- destaque por URL usando `#operationId`;
- layout responsivo e compatível com GitHub Pages;
- nenhuma marcação vermelha das referências faz parte do design.

### Participação e perfil

Ao confirmar participação, o site grava atomicamente:

- `users/{uid}/participations/{operationId}`;
- `operations/{operationId}/participants/{uid}`.

O membro pode criar apenas o próprio registro e somente com estado `confirmed`. A área central antes reservada do Perfil agora apresenta as operações em que o membro confirmou participação.

### Administração de operações

Usuários com `role: admin` recebem controles para:

- criar operações;
- editar operações;
- definir status de inscrições;
- configurar imagens PNG;
- definir a medalha prevista e seu PNG futuro.

Usuários padrão não recebem esses controles e continuam protegidos pelas regras do Firestore.

### Medalhas repetidas e remoção

- Cada concessão de medalha passa a usar um documento com ID automático.
- O mesmo jogador pode receber o mesmo tipo de medalha várias vezes em operações ou datas distintas.
- A janela administrativa serve somente para conceder medalhas.
- A remoção administrativa foi movida para o perfil consultado, preservando cada concessão individual.

## FIRESTORE

O arquivo versionado `firestore.rules` foi atualizado para permitir a criação segura da própria participação e manter a administração das operações protegida por `role: admin`.

**PENDÊNCIA OPERACIONAL:** esta nova versão das regras está no repositório, mas ainda precisa ser publicada no projeto Firebase `exbr-0709` pelo Console ou pela CLI. Até essa publicação, o botão de participação poderá ser recusado pelas regras atualmente ativas.

## NOVOS ARQUIVOS

```text
pages/operacoes.html
css/pages/operacoes.css
js/operations-page.js
js/home-operations.js
data/operacoes.json
```

## MAPA ATUAL RELEVANTE

```text
Home-page/
├── index.html
├── firestore.rules
├── data/
│   ├── medalhas.json
│   ├── operacoes.json
│   └── patentes.json
├── pages/
│   ├── admin.html
│   ├── login.html
│   ├── operacoes.html
│   └── perfil.html
├── css/pages/
│   ├── admin.css
│   ├── home.css
│   ├── login.css
│   ├── operacoes.css
│   └── perfil.css
└── js/
    ├── admin.js
    ├── firebase-client.js
    ├── home-operations.js
    ├── login.js
    ├── main.js
    ├── operations-page.js
    ├── operations.js
    ├── perfil.js
    └── session-ui.js
```


---

# UPDATE — 07/09/2026 — Catálogo editável de medalhas

## OBJETIVO

Permitir que administradores criem novas medalhas e editem os modelos existentes, removendo os emojis temporários e adotando um PNG padrão até que cada condecoração receba uma imagem própria válida.

## IMPLEMENTADO

Commit do repositório de desenvolvimento:

`e540e5857300f02fb98f761ba69c9c8120bf358f` — `feat: adiciona catalogo editavel de medalhas`.

### Catálogo administrativo

- Nova coleção persistente: `medalCatalog/{medalId}`.
- Na primeira abertura administrativa, os seis modelos de `data/medalhas.json` são copiados para o Firestore quando a coleção ainda está vazia.
- Botão `Criar` adicionado ao cabeçalho da janela de medalhas.
- Cada modelo existente recebe uma ação própria de edição.
- O editor permite alterar nome, descrição e caminho/URL do ícone PNG.
- A ação `+` continua separada e serve somente para conceder a medalha ao jogador selecionado.
- A mesma medalha continua podendo ser concedida mais de uma vez em operações e datas diferentes.

### Ícone padrão

Ícone padrão confirmado:

`../assets/icons/dock/recrutamento.png`

- Emojis deixaram de ser usados na exibição das medalhas.
- Medalhas antigas sem `iconUrl` passam a mostrar automaticamente o PNG padrão.
- Novos modelos sem URL também recebem o PNG padrão.
- Um endereço personalizado somente é aceito quando o caminho termina em `.png`.
- Se o PNG personalizado falhar ao carregar, a interface retorna ao `recrutamento.png`.
- O mesmo fallback foi aplicado às medalhas previstas na página de Operações.

### Segurança

O arquivo `firestore.rules` passou a reservar `medalCatalog/{medalId}` exclusivamente para leitura e escrita de administradores.

**PENDÊNCIA OPERACIONAL:** a versão atualizada das regras precisa ser publicada no Firebase `exbr-0709`. Até isso acontecer, o catálogo local continuará visível, mas criação e edição poderão ser recusadas pelo Firestore.

## ARQUIVOS PRINCIPAIS ATUALIZADOS

```text
pages/admin.html
css/pages/admin.css
js/admin.js
data/medalhas.json
pages/perfil.html
css/pages/perfil.css
js/perfil.js
pages/operacoes.html
css/pages/operacoes.css
js/operations-page.js
data/operacoes.json
firestore.rules
FIREBASE.md
README.md
MAPA-SITE.txt
```


---

# UPDATE — 07/09/2026 — Centralização das janelas de medalhas

## CORREÇÃO IMPLEMENTADA

Commit: `d1f9f990081ee7856ae4cc05571044ff69b41b5a` — `fix: centraliza janelas de medalhas`.

- A janela principal do catálogo de medalhas foi centralizada horizontal e verticalmente na tela.
- O editor de criação e edição de medalhas recebeu o mesmo alinhamento.
- A correção neutraliza a margem zerada pelo reset global e mantém a centralização em desktop e celular.


---

# UPDATE — 07/09/2026 — Detalhes das medalhas no Perfil

## IMPLEMENTADO

Commit do repositório de desenvolvimento:

`0675ec19697cb783d143dbd470339f12a72433d0` — `feat: adiciona detalhes das medalhas no perfil`.

- Cada medalha do Perfil passou a ser um controle selecionável por mouse, toque ou teclado.
- Ao selecionar uma medalha, abre uma janela tática centralizada.
- A janela apresenta nome, imagem PNG ampliada, descrição, operação e data da concessão.
- Imagens ausentes, inválidas ou indisponíveis continuam usando `assets/icons/dock/recrutamento.png`.
- Medalhas antigas que possuam `catalogId` consultam o modelo atual em `medalCatalog/{medalId}`, permitindo mostrar descrição e imagem atualizadas.
- O botão administrativo de remoção permanece separado da abertura dos detalhes.
- O catálogo de medalhas passou a permitir leitura para usuários autenticados; criação, edição e exclusão continuam exclusivas para `role: admin`.
- A nova versão de `firestore.rules` precisa ser publicada no Firebase `exbr-0709` para liberar a consulta atualizada do catálogo aos membros.


---

# UPDATE — 07/09/2026 — Área Comunidade e perfis públicos

## IMPLEMENTADO

Último commit do conjunto no repositório de desenvolvimento:

`31bd1ae0371ead65ca079936cccb93af7c4df8b4` — `feat: integra perfis publicos da comunidade`.

- Criada a página protegida `pages/comunidade.html`, acessível somente a usuários autenticados.
- A lista permite pesquisar membros por nome ou patente.
- Cada registro mostra avatar, nome, patente, atividade recente, até cinco medalhas em destaque e o comando `Ver perfil`.
- Os atalhos de Comunidade do cabeçalho móvel e do menu tático inferior agora levam à página dedicada.
- `perfil.html?uid={uid}` permite consultar o perfil público de outro membro.
- Administradores mantêm a consulta administrativa completa; membros comuns recebem somente os dados públicos permitidos.
- O layout é responsivo e preserva a identidade visual futurista EXBR, sem incorporar as anotações vermelhas das referências.

## PRIVACIDADE E FIRESTORE

Nova coleção sanitizada:

`publicProfiles/{uid}`

Campos públicos previstos:

- `displayName`
- `rankId`
- `avatarId`
- `bannerId`
- `featuredMedals` — máximo de cinco
- `recentActivities` — máximo de três
- `updatedAt`

O documento privado `users/{uid}` permanece restrito ao dono e aos administradores. E-mail, função administrativa e demais informações privadas não são copiados para a Comunidade.

A sincronização do perfil público acontece ao abrir a Comunidade ou o próprio Perfil, ao editar avatar/nome/bandeira, ao confirmar participação em operação e quando um administrador altera patente ou medalhas. A abertura da área administrativa também cria/atualiza a identidade pública dos membros existentes.

**PENDÊNCIA OPERACIONAL:** publicar a versão atual de `firestore.rules` no Firebase `exbr-0709`. Sem essa publicação, a página poderá informar que o registro comunitário está indisponível.

## NOVOS ARQUIVOS

```text
pages/comunidade.html
css/pages/comunidade.css
js/comunidade.js
```


---

# UPDATE — 10/09/2026 — Editores administrativos de Operações e Medalhas

## OBJETIVO

Corrigir o posicionamento e os campos de data dos editores, vincular medalhas existentes às operações e dar ao catálogo de medalhas um acesso independente dentro da Área administrativa.

## IMPLEMENTADO

Último commit do conjunto no repositório de desenvolvimento:

`e07c0c05aff0788a9ae500ab6d77427a6727100a` — `feat: aprimora editores administrativos`.

### Operações

- A janela de criação e edição foi fixada e centralizada no meio da tela.
- O antigo campo combinado foi dividido em `Data da operação` e `Horário`.
- Os seletores nativos receberam suporte visual e acionamento compatível com navegadores Chromium/Opera GX.
- Datas anteriores e futuras são permitidas; o resultado continua sendo salvo no Firestore como `startsAt`.
- A medalha prevista agora é escolhida a partir dos modelos existentes em `medalCatalog`.
- A seleção mostra uma prévia com ícone, nome e descrição.
- A operação salva o snapshot `medalCatalogId`, `medalName`, `medalDescription` e `medalIconUrl`.

### Medalhas

- O painel administrativo recebeu as abas `Soldados` e `Catálogo de medalhas`.
- A aba do catálogo permite pesquisar, criar e editar modelos sem abrir a janela de concessão de um membro.
- A concessão de medalhas mantém a seleção de operação e agora identifica claramente o campo `Data da conquista`.
- O administrador pode escolher qualquer data válida, inclusive uma data passada, para registrar a medalha retroativamente.
- O seletor de data também recebeu compatibilidade de abertura para Opera GX.

## ARQUIVOS PRINCIPAIS ATUALIZADOS

```text
pages/admin.html
pages/operacoes.html
css/pages/admin.css
css/pages/operacoes.css
js/admin.js
js/operations-page.js
README.md
FIREBASE.md
MAPA-SITE.txt
```

## FIREBASE

Não foi necessário ampliar permissões nesta etapa. Operações e modelos de medalhas continuam sendo gravados nas coleções já protegidas para administradores pelas regras atuais.


---

# UPDATE — 11/09/2026 — Compatibilidade das imagens de medalhas

## PROBLEMA CORRIGIDO

Alguns membros não conseguiam visualizar imagens de medalhas porque concessões antigas preservavam caminhos ou URLs já substituídos, e diferentes formas de endereço eram interpretadas de maneira inconsistente entre navegador, GitHub Pages e os dois repositórios espelhados.

## IMPLEMENTADO

Último commit do conjunto no repositório de desenvolvimento:

`950d271699e8e019477df7701b8a16fc87a1d4c5` — `Corrige carregamento das imagens de medalhas`.

- Criado o módulo compartilhado `js/medal-images.js`.
- Caminhos locais como `assets/...`, `/assets/...` e `../assets/...` são normalizados para o formato relativo compatível com GitHub Pages.
- Links do GitHub no formato `github.com/.../blob/...png` são convertidos para `raw.githubusercontent.com`.
- Somente URLs HTTPS terminadas em `.png` são aceitas como imagens externas.
- Imagens externas usam `referrerPolicy: no-referrer` para reduzir bloqueios por proteção contra hotlink.
- Falhas de rede, URL removida ou arquivo inválido retornam automaticamente para `assets/icons/dock/recrutamento.png`.
- O fallback recebeu versão de cache para evitar que navegadores mantenham respostas antigas quebradas.
- Perfil, Comunidade, Operações e Área administrativa usam o mesmo resolvedor de imagens.
- Perfis e Comunidade passam a priorizar a definição atual da medalha em `medalCatalog`, inclusive quando a concessão antiga possui um snapshot de imagem desatualizado.
- A página de Operações também prioriza a imagem atual do catálogo para medalhas vinculadas.

## FIREBASE

Nenhuma alteração nas regras do Firestore foi necessária. O fluxo utiliza a leitura autenticada de `medalCatalog` já prevista pelas regras atuais; criação e edição permanecem exclusivas para administradores.

## FLUXO DUPLO

A correção foi publicada em `mrserluiz/Home-page`. O usuário continuará sincronizando manualmente `EXBRClub/Home-page` pelo remote duplo.

## MAPA ATUALIZADO RELEVANTE

```text
Home-page/
├── assets/icons/dock/recrutamento.png
├── js/
│   ├── medal-images.js
│   ├── admin.js
│   ├── comunidade.js
│   ├── operations-page.js
│   └── perfil.js
└── pages/
    ├── admin.html
    ├── comunidade.html
    ├── operacoes.html
    └── perfil.html
```


---

# UPDATE — 11/09/2026 — Perfis detalhados e Galeria da Comunidade

## OBJETIVO

Ampliar a área comunitária com uma galeria de fotos e vídeos hospedados externamente e enriquecer os perfis dos membros com apresentação pessoal, classe favorita e facção favorita em PlanetSide 2.

## IMPLEMENTADO

Último commit do conjunto no repositório de desenvolvimento:

`cbca53e25b2e30e0935ab1c84ab6b7faa2c10ff4` — `feat: adiciona perfis detalhados e galeria comunitária`.

### Perfil do membro

- Campo público `bio` com até 220 caracteres, editável somente pelo dono do perfil.
- A apresentação aparece no centro do perfil em um monitor tecnológico avariado, com scanlines, falha de sinal e tremor discreto de texto.
- Os efeitos respeitam `prefers-reduced-motion`.
- Campo `favoriteClass` para escolher entre Infiltrador, Assalto leve, Médico de combate, Engenheiro, Assalto pesado e MAX.
- Campo `favoriteFaction` para escolher Terran Republic, New Conglomerate, Vanu Sovereignty ou Nanite Systems Operatives.
- Classe favorita exibida no canto inferior esquerdo do cartão do avatar.
- Facção favorita exibida no canto superior direito, abaixo do nome.
- Símbolos geométricos são temporários e a estrutura está preparada para receber ícones oficiais futuramente.
- Perfis antigos recebem valores padrão vazios e são migrados de forma compatível quando as novas regras estiverem ativas.

### Comunidade

- A página `pages/comunidade.html` ganhou as abas `Membros` e `Galeria`.
- A busca de membros agora considera nome, patente, classe e facção.
- Cada membro mostra biografia curta, classe favorita, facção favorita, atividade recente e medalhas em destaque.
- A Galeria EXBR aceita imagens, vídeos diretos, YouTube e Vimeo.
- Nenhum arquivo de mídia é enviado ou salvo no site; apenas URL, título, descrição e metadados são persistidos.
- Somente endereços HTTPS são aceitos.

### Administração

- A Área administrativa ganhou a aba `Galeria`.
- Administradores podem publicar registros escolhendo tipo, URL, título e descrição.
- Administradores podem remover registros existentes.
- A mídia permanece hospedada no serviço externo informado.

### Firestore

Nova coleção:

`communityGallery/{itemId}`

Leitura permitida para usuários autenticados; criação, alteração e remoção continuam exclusivas para administradores.

Os documentos `users/{uid}` e `publicProfiles/{uid}` passam a aceitar:

- `bio`
- `favoriteClass`
- `favoriteFaction`

**PENDÊNCIA OPERACIONAL:** publicar a nova versão de `firestore.rules` no projeto Firebase `exbr-0709`. Sem essa publicação, os novos campos e a Galeria não poderão ser gravados, embora as funções anteriores do portal continuem disponíveis.

## NOVO ARQUIVO

```text
js/community-media.js
```

## MAPA ATUALIZADO RELEVANTE

```text
Home-page/
├── firestore.rules
├── pages/
│   ├── admin.html
│   ├── comunidade.html
│   └── perfil.html
├── css/pages/
│   ├── admin.css
│   ├── comunidade.css
│   └── perfil.css
└── js/
    ├── admin.js
    ├── community-media.js
    ├── comunidade.js
    └── perfil.js
```


---

# UPDATE — 11/09/2026 — Destaques escolhidos e publicações dos membros

## OBJETIVO

Permitir que cada membro escolha quais condecorações aparecem em destaque para a Comunidade e publique seus próprios registros visuais na Galeria EXBR por meio de URLs externas.

## IMPLEMENTADO

Último commit do conjunto no repositório de desenvolvimento:

`cd5ada39f4525d936aef72cbdc68f97ce70399eb` — `feat: permite destaques e publicações dos membros`.

### Medalhas em destaque

- O documento privado `users/{uid}` ganhou o campo `featuredMedalIds`, limitado a cinco IDs de concessões.
- No próprio perfil, cada medalha apresenta uma estrela para adicionar ou remover o destaque.
- Um contador informa quantas das cinco posições estão em uso.
- A ordem escolhida pelo membro é preservada no espelho público `publicProfiles/{uid}.featuredMedals`.
- A Comunidade mostra exatamente as medalhas escolhidas pelo membro.
- Perfis antigos mantêm temporariamente as cinco medalhas mais recentes e são migrados para a seleção explícita ao abrir o Perfil.
- Se um administrador remover uma concessão destacada, o ID também é removido da seleção e o perfil público é sincronizado.

### Publicações na Galeria

- A aba Galeria ganhou um formulário recolhível para membros autenticados.
- O membro escolhe imagem ou vídeo e informa URL HTTPS, título e descrição.
- A publicação registra o UID e o nome público do autor.
- Cada membro pode remover somente as próprias publicações.
- Administradores continuam autorizados a remover qualquer registro e gerenciar a Galeria pelo painel.
- Nenhum arquivo é enviado ao portal; somente URL e metadados são armazenados.

### Firestore

As regras foram ampliadas para:

- permitir ao dono atualizar `featuredMedalIds`, com no máximo cinco itens;
- permitir criação de registros em `communityGallery` por usuário autenticado, com validação dos campos e autoria;
- permitir remoção pelo próprio autor ou por administrador;
- manter a edição de publicações exclusiva para administradores.

**PENDÊNCIA OPERACIONAL:** publicar a versão atual de `firestore.rules` no projeto Firebase `exbr-0709`. Sem isso, a escolha de destaques e as publicações dos membros serão recusadas pelo Firestore.

## FLUXO DUPLO

O conjunto foi publicado em `mrserluiz/Home-page`. O usuário deve sincronizar `EXBRClub/Home-page` pelo remote duplo após atualizar a cópia local.


---

# UPDATE — 11/09/2026 — Registro imediato e lista de membros em tempo real

## PROBLEMA

Um usuário podia existir no Firebase Authentication sem aparecer no painel administrativo. O cadastro criava primeiro a conta de autenticação, mas deixava a criação de `users/{uid}` para a abertura posterior do Perfil. Além disso, o painel administrativo consultava a coleção de usuários somente uma vez ao carregar.

## CORREÇÃO

Último commit do conjunto no repositório de desenvolvimento:

`15649f8fa87dd538ef47c3a76ceed02087ad671a` — `fix: registra e atualiza novos membros`.

- O cadastro passa a criar imediatamente `users/{uid}` com função `member`, patente `soldado` e preferências padrão.
- Mantido fallback compatível com regras antigas do Firestore.
- Se a conta do Authentication for criada e a gravação do perfil falhar, o usuário é encaminhado ao Perfil, cuja rotina existente tenta reparar o documento.
- O painel administrativo usa escuta em tempo real na coleção `users`.
- Novos documentos aparecem sem precisar atualizar manualmente a página.
- O espelho `publicProfiles/{uid}` continua sendo sincronizado pelo administrador.

## CONTA CRIADA ANTES DA CORREÇÃO

Uma conta que já esteja somente no Firebase Authentication precisa entrar novamente no portal e abrir o Perfil para criar/reparar `users/{uid}`. Depois disso, aparecerá automaticamente no painel administrativo.


---

# UPDATE — 12/09/2026 — Arquivamento permanente de imagens no Cloudinary

## OBJETIVO

Impedir que imagens desapareçam quando URLs externas expiram, mudam ou bloqueiam carregamento direto, mantendo o Firebase no plano gratuito.

## SERVIÇO CONFIGURADO

- Plataforma: Cloudinary.
- Cloud name público: `uofznsju`.
- Upload preset sem assinatura: `exbr_site_images`.
- Pasta de ativos: `exbr-site`.
- Sobrescrita desativada e identificadores únicos.
- API Secret não é usado nem exposto no site.

## IMPLEMENTADO

Último commit do conjunto no repositório de desenvolvimento:

`173a167ac5f07de3ef38bc36b2745c4267732c6b` — `feat: arquiva imagens externas no Cloudinary`.

- Criado `js/cloudinary-images.js` como módulo central de importação.
- URLs HTTPS externas são enviadas ao Cloudinary uma única vez.
- Links `github.com/.../blob/...` são convertidos para o arquivo bruto antes da importação.
- A URL gravada utiliza HTTPS e entrega transformada em PNG.
- Caminhos locais em `assets/` continuam locais e não são duplicados.
- Tempo limite de 45 segundos e mensagens de erro legíveis.
- O preset foi testado com `assets/icons/dock/recrutamento.png` e retornou uma cópia PNG válida na pasta `exbr-site`.

### Medalhas

- O editor aceita PNG, JPG, JPEG ou WebP por URL HTTPS.
- A imagem é arquivada antes da gravação em `medalCatalog`.
- URLs externas antigas do catálogo são migradas quando um administrador abre a Área administrativa.
- Sem imagem válida, permanece o fallback `recrutamento.png`.

### Operações

- O editor aceita caminho local ou URL externa.
- URLs externas são arquivadas antes de salvar a operação.
- Operações antigas do Firestore são migradas quando um administrador abre a página dedicada de Operações.

### Galeria

- Fotos publicadas por membros ou administradores são arquivadas antes da criação do documento.
- Vídeos diretos, YouTube e Vimeo permanecem hospedados externamente.
- Fotos antigas são migradas quando um administrador abre a Área administrativa.
- O Firestore continua armazenando apenas URL e metadados.

## SEGURANÇA E MANUTENÇÃO

O preset é público por necessidade do GitHub Pages, mas deve permanecer limitado a imagens, tamanho máximo reduzido, pasta exclusiva, nomes únicos e sobrescrita desativada. A remoção de um registro no Firestore não exclui automaticamente o arquivo do Cloudinary; a limpeza física pode ser feita na Biblioteca de Mídia ou receber uma função protegida futuramente.

## FIREBASE

Nenhuma alteração adicional nas regras do Firestore foi necessária nesta etapa. O Cloudinary substitui o Firebase Storage, que exigiria o plano Blaze.



---

# UPDATE — 12/09/2026 — Migração automática centralizada de imagens

## DECISÃO

A migração das imagens externas antigas foi centralizada na abertura da Área administrativa. Uma única visita de um administrador ao painel verifica medalhas, fotos da Galeria e imagens de operações, importa os arquivos elegíveis para o Cloudinary e atualiza as respectivas URLs no Firestore.

## COMPORTAMENTO

- A execução ocorre automaticamente após a autenticação administrativa.
- Não é necessário abrir separadamente o editor de Operações.
- Caminhos locais do próprio site não são duplicados.
- Vídeos permanecem externos.
- Se uma importação falhar, a URL original é preservada e uma nova tentativa ocorre no próximo acesso administrativo.
- Por ser um site estático no GitHub Pages, a rotina depende da abertura do painel e não executa em segundo plano quando o site está fechado.

## FIREBASE

Nenhuma mudança nas regras do Firestore foi necessária.

## PUBLICAÇÃO

Último commit do conjunto no repositório de desenvolvimento:

`6746026048a0e841680a21355db98582e5cb3343` — `Documenta migração automática de imagens`.


---

# UPDATE — 12/09/2026 — Zoom de inspeção das medalhas

## IMPLEMENTADO

Último commit do conjunto no repositório de desenvolvimento:

`7853b9322b180a0bc061fd68b9bb9b2c28678509` — `Atualiza mapa do perfil`.

- A imagem ampliada da medalha no Perfil ganhou zoom de inspeção de 2,4×.
- O ponto ampliado acompanha a posição do cursor, no estilo de visualização de produtos em lojas virtuais.
- A área mostra a orientação discreta `MOVA PARA INSPECIONAR` antes da interação.
- O zoom é ativado somente em computadores com mouse ou ponteiro preciso e largura superior a 768 px.
- Celulares e dispositivos de toque mantêm a exibição estática anterior.
- Ao retirar o cursor ou fechar a janela, a imagem retorna automaticamente ao estado normal.
- Nenhuma mudança nas regras do Firebase foi necessária.


---

# UPDATE — 12/09/2026 — Inventário de medalhas e destaque da Galeria

## OBJETIVO

Reorganizar o crescente histórico de condecorações como um inventário visual de jogo, facilitar a escolha de destaques e permitir concessões diretamente no Perfil, além de priorizar a Galeria na Comunidade e corrigir problemas de exibição mobile.

## IMPLEMENTADO

Último commit do conjunto no repositório de desenvolvimento:

`14138df89f2f81000716c467e8f36cc486aadb55` — `Atualiza mapa do perfil e comunidade`.

### Inventário no Perfil

- O bloco mantém o cabeçalho, a descrição e o estado vazio anteriores.
- O contador numérico do canto superior direito foi removido.
- Com medalhas, o conteúdo usa três colunas e nove slots iniciais.
- Acima de nove itens, novas linhas são criadas e consultadas pela rolagem vertical existente.
- Slots não ocupados permanecem visíveis como espaços para futuras condecorações.
- Ao passar o mouse sobre um item, seu nome aparece sobre o slot.
- O clique continua abrindo a janela com imagem, descrição, operação, data e zoom de inspeção no computador.
- Cada medalha possui uma estrela mínima no canto inferior direito; `☆` indica normal e `★` indica favorita.

### Favoritos

- A janela de detalhes ganhou o botão `Favoritar medalha ☆` no canto inferior direito.
- O botão explica que até cinco medalhas favoritas aparecem na área Membros da Comunidade.
- O limite existente de cinco destaques foi preservado.
- Inventário, janela de detalhes e `publicProfiles/{uid}.featuredMedals` são sincronizados após a alteração.

### Concessão administrativa pelo Perfil

- Contas administrativas veem um botão `+` no cabeçalho do bloco de medalhas ao consultar um perfil.
- O botão abre uma janela grande com pesquisa, operação e data retroativa.
- O catálogo administrativo usa nove colunas no computador e espaços vazios para manter a aparência de inventário.
- Selecionar um item concede a medalha ao perfil consultado.
- A mesma medalha continua podendo ser concedida em operações ou datas diferentes.

### Comunidade e mobile

- A página Comunidade passa a abrir inicialmente na Galeria.
- A ordem visual das abas foi invertida para `Galeria` e `Membros`.
- No mobile, as cinco medalhas favoritas usam uma grade ajustável e aparecem juntas, sem rolagem horizontal.
- O avatar do Perfil recebeu uma camada de renderização mais estável no mobile, removendo o filtro custoso nessa largura e evitando que desapareça após descer e subir a página.

## FIREBASE

Nenhuma alteração nas regras do Firestore foi necessária. A concessão pelo Perfil continua restrita a administradores pelas regras existentes da subcoleção `users/{uid}/medals`.


---

# UPDATE — 12/09/2026 — Símbolos visuais das facções

## IMPLEMENTADO

Último commit do conjunto no repositório de desenvolvimento:

`5a2841466bbe5a72dace2d94a3ad9b5d96fa36d0` — `Atualiza mapa dos recursos de facção`.

- Recebidos quatro símbolos visuais fornecidos pelo usuário.
- Mapeamento confirmado: imagem 1 New Conglomerate, imagem 2 Terran Republic, imagem 3 Vanu Sovereignty e imagem 4 Nanite Systems Operatives.
- Os arquivos recebidos possuíam extensão `.webp`, mas conteúdo JPEG sem transparência.
- As quatro imagens foram arquivadas permanentemente no Cloudinary da EXBR, na área de facções, com entrega otimizada em 256 × 256 px.
- Os símbolos temporários foram substituídos nos quatro botões de escolha de facção do Perfil.
- A facção continua persistida no Firestore somente pelo identificador `nc`, `tr`, `vs` ou `nso`.
- O cartão do Perfil passa a mostrar o ícone da facção escolhida no marcador superior.
- A lista de membros da Comunidade também mostra o símbolo ao lado do nome completo da facção.
- Nomes, títulos e rótulos acessíveis foram preservados.
- Nenhuma alteração nas regras do Firebase foi necessária.


---

## Atualização — 12/09/2026 — Ícones holográficos de classe e marcadores de perfil

**Commits do site:**
- `2c1e02e91a28bb96054b6dfd256257357ede3aa7` — adiciona ícones holográficos das classes.
- `300b728e5c487f75bc3cc021a5cdae9f6b6ca9e3` — aprimora marcadores de classe e facção.

- Mapeamento de classes confirmado: Infiltrador, Assalto leve, Médico de combate, Engenheiro, Assalto pesado e MAX.
- Os seis símbolos enviados foram recortados com canal alfa real e receberam tratamento holográfico azul, mais intenso no centro e suave nas extremidades.
- Os ícones foram publicados no Cloudinary em `exbr-site/classes`, incluídos como cópia de segurança em `assets/classes` e ligados ao seletor de classe, ao marcador do Perfil e à Comunidade.
- Os quatro emblemas de facção tiveram o fundo preto removido, preservando cores e formas, e foram publicados no Cloudinary em `exbr-site/factions-v2`.
- Os arquivos transparentes de facção também ficam versionados em `assets/factions`.
- Quando classe ou facção ainda não foi selecionada, o marcador usa `assets/icons/dock/recrutamento.png` apenas como indicação visual; ele não aparece como opção.
- Depois da seleção, o texto inferior do marcador passa de “Classe” ou “Facção” para o nome escolhido.
- O tamanho desse texto é calculado conforme o comprimento do nome para permanecer dentro do marcador.
- A persistência no Firestore continua usando apenas os identificadores existentes; nenhuma mudança de regra ou migração de dados foi necessária.
