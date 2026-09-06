# UPDATE — ETHERCRAFT SITE
## Firebase Authentication + Perfil do Jogador
### Data: 06/09/2026

---

# 1. OBJETIVO DESTA ETAPA

Foi iniciada a implementação do sistema de contas do site EtherCraft.

Objetivos definidos:

- permitir cadastro de jogadores;
- permitir login/logout;
- manter sessão entre as páginas;
- criar perfil individual;
- vincular nome de exibição e nick do Minecraft;
- criar sistema fechado de avatares;
- transformar Login em Perfil quando autenticado;
- registrar favoritos e páginas recentes;
- preparar progresso de eventos;
- futuramente usar Firestore para sincronização e permissões administrativas.

Foi criado um projeto Firebase separado chamado:

`EtherCraft`

Este Firebase é exclusivo para o site principal e NÃO deve ser confundido com integrações Firebase anteriores do módulo Amigo Secreto.

---

# 2. FIREBASE — ESTADO CONFIRMADO

Projeto Firebase:

`EtherCraft`

Project ID:

`ethercraft-378c3`

Authentication configurado com:

`E-mail/Senha`

Domínio autorizado:

`mrserluiz.github.io`

Cadastro foi testado com sucesso.

Login foi testado com sucesso.

Sessão autenticada foi testada com sucesso.

E-mail de verificação foi recebido e confirmado.

O primeiro e-mail havia sido direcionado para Spam/Lixo eletrônico.

Portanto:

| Sistema | Estado |
|---|---|
| Firebase Web App | ✅ FUNCIONANDO |
| Email/Password | ✅ FUNCIONANDO |
| Cadastro | ✅ FUNCIONANDO |
| Login | ✅ FUNCIONANDO |
| Logout | ✅ FUNCIONANDO |
| Sessão persistente | ✅ FUNCIONANDO |
| Verificação de e-mail | ✅ FUNCIONANDO |
| Domínio GitHub Pages | ✅ AUTORIZADO |
| Firestore | ❌ AINDA NÃO IMPLEMENTADO |

---

# 3. ALERTA DA API KEY

GitHub Secret Scanning identificou a Firebase Web API Key presente em:

`js/firebase.js`

Foi investigado que esta é uma Firebase Web API Key utilizada no frontend.

Decisão atual:

- NÃO revogar automaticamente a chave;
- NÃO ativar cobrança;
- NÃO contratar Google Cloud;
- NÃO utilizar nenhuma configuração que obrigue ativação de billing neste momento.

O usuário informou que não pode investir financeiramente nesta etapa.

O desenvolvimento atual deve permanecer compatível com o plano gratuito/Spark sempre que possível.

IMPORTANTE:

Nunca colocar no frontend:

- Service Account JSON;
- Firebase Admin private key;
- `client_secret`;
- GitHub token;
- Gemini API key;
- qualquer credencial administrativa real.

---

# 4. ARQUIVOS PRINCIPAIS DO LOGIN

## `js/firebase.js`

Responsável por:

- inicializar Firebase;
- inicializar Firebase Authentication;
- disponibilizar `auth`;
- configurar persistência da autenticação.

Firebase JS utilizado:

`12.18.0`

---

## `js/auth.js`

Sistema implementado:

- criar conta;
- login por e-mail/senha;
- logout;
- recuperação de senha;
- envio de verificação de e-mail;
- reenvio de verificação;
- nome de exibição;
- tratamento de erros;
- publicação do estado da autenticação;
- redirecionamento após login.

Evento utilizado:

`ethercraft:auth-changed`

Objeto global:

`window.EtherCraftAuth`

O login bem-sucedido agora encaminha o jogador para:

`pages/perfil.html`

Se um usuário já autenticado tentar acessar:

`pages/login.html`

ele deve ser encaminhado para o Perfil.

---

# 5. CADASTRO

O cadastro atualmente possui:

- Nome de exibição;
- Nome no Minecraft;
- E-mail;
- Senha;
- Confirmação de senha.

O campo:

`Nome no Minecraft`

foi adicionado porque a conta do site deverá representar também a identidade do jogador dentro do servidor EtherCraft.

Atualmente o nick Minecraft ainda não está no Firestore.

Enquanto o banco não for implementado, dados complementares do perfil utilizam armazenamento local por UID.

---

# 6. PERFIL DO JOGADOR

Página criada:

`pages/perfil.html`

Script:

`js/profile.js`

O perfil atualmente possui:

- avatar;
- nome de exibição;
- nome Minecraft;
- e-mail;
- status de verificação;
- edição do perfil;
- logout;
- páginas favoritas;
- páginas visitadas recentemente;
- estrutura de progresso de eventos.

O antigo botão:

`Abrir Wiki`

foi REMOVIDO do perfil.

Motivo:

A Wiki já possui acesso pelo menu principal e o botão era redundante.

---

# 7. SISTEMA DE AVATAR

Decisão de design:

O EtherCraft NÃO permitirá que jogadores utilizem qualquer imagem externa através de URL.

A ideia anterior de:

`URL personalizada para foto`

foi REMOVIDA.

O sistema passa a utilizar somente avatares permitidos pelo EtherCraft.

Estrutura planejada:

## Emojis

Disponíveis imediatamente como avatares padrão.

Exemplos:

- 🧙
- 👑
- 🐉
- ⚔️
- etc.

## Fotos oficiais

Futuramente serão adicionados arquivos `.png` definidos pela administração.

Pasta proposta:

`assets/images/avatars/`

Exemplo futuro:

`avatar_01.png`
`avatar_02.png`
`avatar_03.png`

No `profile.js` existe estrutura preparada para receber essas imagens.

---

# 8. EDIÇÃO DO AVATAR

A foto do jogador funciona como botão.

Normalmente aparece apenas:

`avatar`

Ao passar o mouse sobre ela:

`Editar foto`

Clicando, abre um menu centralizado na tela.

Estrutura:

Escolher foto de perfil

Emojis
[ opções ]

Fotos
[ PNGs oficiais futuramente ]

[ Fechar e salvar ]

O usuário escolhe uma opção e:

`Fechar e salvar`

fecha o menu e mantém automaticamente a escolha.

---

# 9. CORREÇÃO VISUAL DO AVATAR

Durante os testes apareceu um artefato:

`linha horizontal atravessando o círculo do avatar`

Também foi identificado que o emoji parecia não estar perfeitamente centralizado.

Foram realizadas várias correções até localizar a estrutura problemática.

Solução final:

- foto e fallback passaram a ocupar a mesma área;
- posicionamento absoluto dentro do círculo;
- centralização explícita;
- `object-position: center center`;
- elementos `[hidden]` são realmente removidos visualmente;
- botão circular passou a ser o próprio elemento interativo;
- removida estrutura de botão invisível sobreposto.

Após a última correção o usuário confirmou:

`perfeito`

Portanto:

Avatar circular:
✅ CORRIGIDO

Centralização:
✅ CORRIGIDA

Linha horizontal:
✅ CORRIGIDA

Hover "Editar foto":
✅ FUNCIONANDO

Menu de avatar:
✅ CENTRALIZADO

---

# 10. SESSÃO

Objetivo definido:

A conta NÃO deve desaparecer simplesmente porque o usuário mudou de página.

A sessão deve permanecer enquanto o jogador utiliza o site.

Foi criada uma política própria de inatividade:

`12 horas`

Enquanto houver atividade, a sessão permanece.

Atividades monitoradas incluem interação com a página.

Depois de aproximadamente 12 horas sem atividade:

`logout automático`

Também permanece disponível:

`logout manual`

Portanto:

| Sessão | Estado |
|---|---|
| Entre páginas | ✅ |
| Logout manual | ✅ |
| Logout por inatividade | ✅ 12h |

---

# 11. BOTÃO CIRCULAR GLOBAL DO PERFIL

Quando autenticado, existe um botão circular de perfil.

Ele utiliza o avatar escolhido pelo jogador.

O objetivo é fornecer acesso rápido ao perfil enquanto navega pelo site.

Quando deslogado:

o botão não deve aparecer.

Quando logado:

o botão leva para:

`pages/perfil.html`

---

# 12. MENU PRINCIPAL

Foi definida uma regra global para a navegação.

Ordem oficial:

Home
Eventos
Regras
Como Jogar
Wiki
Login / Perfil

Portanto:

`Wiki`

deve ser SEMPRE o penúltimo item.

`Login / Perfil`

deve ser SEMPRE o último item.

---

# 13. LOGIN → PERFIL

Quando NÃO autenticado:

`Login`

Quando autenticado:

`Perfil`

Portanto o mesmo espaço do menu representa a conta.

Exemplo deslogado:

Home
Eventos
Regras
Como Jogar
Wiki
Login

Exemplo logado:

Home
Eventos
Regras
Como Jogar
Wiki
Perfil

---

# 14. PROBLEMA DESCOBERTO EM REGRAS E EVENTOS

Durante testes foi descoberto que:

`pages/regras.html`

e:

`pages/eventos.html`

ainda apresentavam o menu antigo.

Investigação mostrou que essas páginas carregavam:

`js/main.js`

usando caminho incorreto.

Como estão dentro de `/pages/`, deveriam utilizar:

`../js/main.js`

Por causa disso, a lógica global de autenticação/menu não estava sendo executada nessas páginas.

Foi corrigido.

Também foi corrigida diretamente a ordem dos links no HTML.

Estado:

`pages/regras.html`
✅ CORRIGIDO

`pages/eventos.html`
✅ CORRIGIDO

---

# 15. REGRA DE PATHS DO GITHUB PAGES

Manter esta regra:

## Root

`index.html`

Usar:

`pages/...`

---

## Dentro de `/pages/`

Usar:

`../index.html`

`../js/...`

`../css/...`

ou arquivos irmãos diretamente:

`wiki.html`
`perfil.html`
`login.html`

---

## Dentro de `/pages/wiki/`

Usar:

`../../index.html`

`../../js/...`

`../../css/...`

`../../data/...`

GitHub Pages diferencia maiúsculas/minúsculas.

A pasta correta é:

`pages/`

---

# 16. FAVORITOS

Perfil possui:

`⭐ Páginas favoritas`

O usuário pode marcar páginas acessadas como favoritas.

Atualmente:

`localStorage`

Portanto:

✅ funciona no navegador atual

❌ ainda não sincroniza entre dispositivos

Exemplo:

PC → favoritos próprios locais

Celular → ainda não recebe os mesmos favoritos

Sincronização ficará para Firestore.

---

# 17. VISITADAS RECENTEMENTE

Perfil possui:

`🕘 Visitadas recentemente`

O site registra automaticamente páginas navegadas.

Atualmente o histórico é local.

Objetivo futuro:

sincronizar através da conta do jogador.

---

# 18. PROGRESSO DE EVENTOS

Foi criada no perfil a seção:

`🏆 Progresso de eventos`

Neste momento é SOMENTE estrutura visual.

Ainda NÃO existe conexão entre eventos e conta.

Estado:

Interface:
✅ EXISTE

Dados reais:
❌ NÃO IMPLEMENTADOS

Firestore:
❌ NÃO IMPLEMENTADO

Integração com eventos:
❌ NÃO IMPLEMENTADA

Não tratar `0%` atual como progresso real do jogador.

---

# 19. FIRESTORE — PRÓXIMA GRANDE ETAPA

Após estabilização completa da interface de conta, a próxima etapa planejada é Cloud Firestore.

Estrutura proposta:

usuarios/
  {uid}/
    nome
    email
    role
    minecraftNick
    avatar
    favoritos
    recentes
    criadoEm

Possíveis cargos:

player
moderator
admin

Arquitetura:

Firebase Authentication
        ↓
       UID
        ↓
Firestore
usuarios/{uid}
        ↓
role + dados do jogador

---

# 20. SEGURANÇA DOS CARGOS

IMPORTANTE:

Nunca confiar somente em JavaScript como:

`role = "admin"`

para proteger funções administrativas.

Firestore Security Rules deverá controlar autorização real.

Jogadores comuns NÃO poderão alterar o próprio:

`role`

Administração deverá controlar a promoção para:

`moderator`

ou:

`admin`

---

# 21. WIKI + ADMIN

A Wiki já possui preparação para verificar:

`window.EtherCraftAuth?.currentUser?.role === 'admin'`

Porém o sistema de roles ainda NÃO está conectado.

Portanto:

Editor administrativo real:
❌ NÃO LIBERADO

Firestore:
❌ NÃO CONECTADO

Publicação entre dispositivos:
❌ NÃO IMPLEMENTADA

O editor atual não deve ser tratado como sistema administrativo seguro até Firestore + Rules serem implementados.

---

# 22. ESTADO ATUAL DO PROJETO

EtherCraft
│
├── pages/
│   ├── login.html
│   │   └── ✅ autenticação
│   │
│   ├── perfil.html
│   │   ├── ✅ avatar
│   │   ├── ✅ nome
│   │   ├── ✅ nick Minecraft
│   │   ├── ✅ e-mail
│   │   ├── ✅ favoritos
│   │   ├── ✅ recentes
│   │   └── 🟡 progresso de eventos visual
│   │
│   ├── eventos.html
│   │   └── ✅ menu corrigido
│   │
│   ├── regras.html
│   │   └── ✅ menu corrigido
│   │
│   ├── wiki.html
│   │
│   └── wiki/
│       ├── mecanicas.html
│       ├── receitas.html
│       ├── bestiario.html
│       ├── dimensoes.html
│       ├── encantamentos.html
│       └── economia.html
│
├── js/
│   ├── firebase.js
│   │   └── ✅ Firebase/Auth
│   │
│   ├── auth.js
│   │   └── ✅ cadastro/login
│   │
│   ├── profile.js
│   │   └── ✅ perfil/avatar
│   │
│   ├── main.js
│   │   ├── ✅ conta global
│   │   ├── ✅ Login ↔ Perfil
│   │   ├── ✅ histórico
│   │   └── ✅ inatividade 12h
│   │
│   ├── wiki.js
│   ├── wiki-content.js
│   └── wiki-motion.js
│
├── data/
│   └── wiki/
│       ├── receitas.json
│       ├── mobs.json
│       ├── encantamentos.json
│       ├── dimensoes.json
│       ├── economia.json
│       └── mecanicas.json
│
├── assets/
│   └── images/
│       └── avatars/
│           └── ⏳ PROPOSTO — PNGs oficiais futuros
│
└── Firebase EtherCraft
    ├── Authentication
    │   ├── ✅ Email/Password
    │   ├── ✅ Cadastro
    │   ├── ✅ Login
    │   ├── ✅ Sessão
    │   └── ✅ Verificação de e-mail
    │
    └── Firestore
        └── ⏳ PRÓXIMA ETAPA

---

# 23. DECISÕES CONSOLIDADAS

1. Firebase principal do site será separado de sistemas antigos.

2. Authentication usa e-mail/senha.

3. Perfil é obrigatório como área central da conta.

4. Nick Minecraft faz parte da identidade do jogador.

5. Não permitir avatar externo por URL.

6. Avatares serão:
   - emojis oficiais;
   - PNGs oficiais definidos pelo EtherCraft.

7. Login vira Perfil automaticamente quando autenticado.

8. Login/Perfil é sempre o ÚLTIMO item do menu.

9. Wiki é sempre o PENÚLTIMO item.

10. Sessão permanece entre páginas.

11. Logout automático somente após aproximadamente 12h de inatividade.

12. Favoritos e recentes funcionam localmente nesta fase.

13. Firestore posteriormente sincronizará dados entre dispositivos.

14. Progresso de eventos será vinculado à conta futuramente.

15. Roles deverão ser protegidas por Firestore Security Rules.

16. Não ativar billing/Google Cloud pago sem necessidade e sem autorização explícita do usuário.

---

# 24. PRÓXIMO PASSO RECOMENDADO

Não expandir vários sistemas simultaneamente.

Authentication e interface de Perfil já atingiram estado funcional.

Próxima etapa lógica:

`FIRESTORE — PERFIL PERSISTENTE`

Objetivo inicial:

criar:

usuarios/{uid}

e migrar progressivamente:

- nome;
- minecraftNick;
- avatar;
- role;
- favoritos;
- dados necessários da conta.

Depois:

`ROLE ADMIN`

e somente então conectar:

`WIKI ADMIN`

e:

`PROGRESSO DE EVENTOS`

---

# STATUS DO UPDATE

AUTHENTICATION:
✅ FUNCIONAL

PERFIL:
✅ FUNCIONAL

AVATAR:
✅ FUNCIONAL / ARTEFATO CORRIGIDO

NAVEGAÇÃO:
✅ CORRIGIDA

FAVORITOS:
🟡 LOCAL

RECENTES:
🟡 LOCAL

PROGRESSO DE EVENTOS:
🟡 SOMENTE INTERFACE

FIRESTORE:
❌ NÃO IMPLEMENTADO

ROLES:
❌ NÃO IMPLEMENTADOS

WIKI ADMIN SEGURO:
❌ NÃO IMPLEMENTADO

PRÓXIMA FASE:
→ FIRESTORE / PERFIL PERSISTENTE
# EtherCraft — Memória do Projeto Site

## Identificação

**Projeto:** EtherCraft — Site Oficial
**Repositório principal:** `https://github.com/mrserluiz/EtherCraft`
**Memória persistente:** `https://github.com/mrserluiz/MANUAL-MEMORY-SYSTEM`
**Hospedagem:** GitHub Pages
**URL pública:** `https://mrserluiz.github.io/EtherCraft/`

---

# Objetivo do Projeto

Criar e manter o site oficial do servidor Minecraft **EtherCraft**, utilizando uma arquitetura estática, modular, responsiva e preparada para expansão futura.

O site deve funcionar como:

* Página institucional do servidor.
* Central de navegação para jogadores.
* Página de regras.
* Página de eventos.
* Área “Como Jogar”.
* Futuras páginas de login, staff e outros sistemas.
* Hospedagem de eventos especiais reutilizáveis.
* Interface administrativa para sistemas específicos.

O site deve permanecer compatível com **GitHub Pages**.

---

# Tecnologias

## CONFIRMADO

* HTML5
* CSS3
* JavaScript Vanilla
* GitHub Pages
* Firebase/Firestore em módulos que exigem persistência
* JSON para dados estáticos
* Manifest/PWA
* Design responsivo
* Mobile First
* SEO básico e Open Graph

---

# Identidade Visual

## CONFIRMADO

O site segue estética baseada em tons de:

* Roxo escuro
* Indigo
* Lilás
* Branco/esbranquiçado

Cores já utilizadas:

```text
#0b0614
#28104f
#8d65d1
#fff9ff
```

A direção artística deve transmitir:

* Fantasia
* Medieval
* Magia
* Minecraft
* Visual moderno
* Interface limpa

---

# Cabeçalho da Home

## CONFIRMADO

A página inicial utiliza:

* Logo EtherCraft centralizada.
* Logo responsiva para desktop e celular.
* Header fixo inicialmente.
* Efeito de fade-out da logo ao rolar a página.
* Fade-in ao retornar ao topo.
* A logo acompanha o usuário apenas no trecho inicial da Home.

Arquivo da logo:

```text
assets/images/Ether_Logo.png
```

Esse comportamento é específico da **Home** e não deve ser automaticamente aplicado às páginas internas.

---

# Menu de Navegação

## CONFIRMADO

O menu principal possui:

```text
Home | Eventos | Regras | Como Jogar | Login
```

Características:

* Barra roxa/lilás.
* Navegação fixa no topo.
* Deve permanecer disponível durante toda a rolagem.
* Botões retangulares integrados visualmente à barra.
* Hover suave.
* Responsivo.
* Estrutura fácil para adicionar novos links.

## Regra de Caminhos

Na Home:

```html
pages/regras.html
pages/eventos.html
pages/login.html
#como-jogar
```

Nas páginas dentro de `/pages/`:

```html
../index.html
../pages/regras.html
../pages/eventos.html
../pages/login.html
../index.html#como-jogar
```

Não utilizar caminhos começando apenas por:

```text
/pages/
```

porque no GitHub Pages isso aponta para:

```text
https://mrserluiz.github.io/pages/
```

e ignora `/EtherCraft/`.

---

# Home

## CONFIRMADO

A Home utiliza uma seção `.hero`.

Características principais:

* Grande destaque inicial.
* Conteúdo centralizado.
* Fundo em gradiente roxo.
* Logo grande.
* Navegação fixa.
* Hero responsivo.
* Botões de ação.
* Seções institucionais.

Arquivo específico:

```text
css/pages/home.css
```

---

# Páginas Internas

## DECISÃO DE ARQUITETURA

As páginas internas não devem reutilizar integralmente o comportamento visual da `.hero` da Home.

Exemplos:

* Regras
* Eventos
* Login
* Futuras páginas internas

A Home pode possuir:

```text
.site-main
.hero
.site-header
```

As páginas internas devem evoluir para algo como:

```text
.page-main
.page-header
.page-content
```

Objetivo:

* Evitar grandes espaços verticais herdados da Home.
* Manter navegação consistente.
* Permitir layouts compactos.
* Preservar a identidade visual.

---

# CSS Modular

## CONFIRMADO

Estrutura adotada:

```text
css/
├── reset.css
├── base.css
├── components.css
└── pages/
```

Responsabilidades:

### `reset.css`

Normalização dos estilos padrão do navegador.

### `base.css`

Responsável por:

* Variáveis de cor.
* Tipografia.
* Fundo.
* Containers.
* Tokens globais.
* Espaçamentos básicos.
* Transições.

### `components.css`

Responsável por componentes reutilizáveis:

* `.site-header`
* `.brand-logo`
* `.site-nav`
* `.nav-shell`
* `.nav-link`
* `.btn`
* `.btn-primary`
* `.btn-secondary`
* `.cards-grid`
* `.feature-card`
* `.content-panel`

### `pages/*.css`

Responsável exclusivamente pelo comportamento específico de cada página.

---

# Estrutura Visual Atual do components.css

## CONFIRMADO

Já possui:

* Header fixo.
* Fade do header.
* Logo responsiva.
* Navbar fixa.
* Barra com gradiente.
* Hover dos links.
* Botões reutilizáveis.
* Cards.
* Painéis de conteúdo.
* Media queries para mobile e desktop.

Não reescrever esse arquivo sem necessidade.

Preservar o design atual sempre que possível.

---

# Layout da Página Regras

## EM DESENVOLVIMENTO

A página:

```text
pages/regras.html
```

deve manter a estética do site principal, mas sem o grande espaço da Home.

Planejamento:

* Menu principal no topo.
* Conteúdo central.
* Menu lateral esquerdo com tópicos.
* Caixa principal de regras à direita/centro.
* Navegação por âncoras.

Exemplo conceitual:

```text
[ MENU GLOBAL ]

[ Tópicos ] [ Conteúdo das regras ]
[ Tópicos ] [ Conteúdo das regras ]
[ Tópicos ] [ Conteúdo das regras ]
```

No mobile:

```text
[ MENU GLOBAL ]

[ TÓPICOS HORIZONTAIS ]

[ CONTEÚDO ]
```

---

# Layout da Página Eventos

## EM DESENVOLVIMENTO

Página:

```text
pages/eventos.html
```

Deve utilizar o mesmo padrão visual das páginas internas.

Cabeçalho conceitual:

```html
<p class="eyebrow">EtherCraft</p>
<h1>Eventos</h1>
<p>Eventos da Comunidade de EtherCraft</p>
```

A `.hero` da Home não deve necessariamente ser utilizada permanentemente nessa página.

---

# Conteúdo Centralizado

## CONFIRMADO

O projeto utiliza:

```text
.container
.content-panel
.hero-content
```

Textos institucionais podem utilizar blocos centrais.

Para textos longos, preferir alinhamento à esquerda dentro de containers centralizados.

Títulos podem permanecer centralizados.

---

# Imagens dentro do Conteúdo

Imagens podem ser inseridas entre parágrafos através de `<img>` ou preferencialmente `<figure>`.

Exemplo:

```html
<figure class="content-figure">
  <img src="..." alt="...">
  <figcaption>...</figcaption>
</figure>
```

Devem ser responsivas.

---

# Favicons e PWA

## CONFIRMADO

Arquivos existentes:

```text
assets/icons/
├── android-chrome-192x192.png
├── android-chrome-512x512.png
├── apple-touch-icon.png
├── favicon-16x16.png
├── favicon-32x32.png
├── favicon.ico
└── site.webmanifest
```

Na Home:

```html
href="assets/icons/..."
```

Nas páginas em `/pages/`:

```html
href="../assets/icons/..."
```

O manifest deve considerar o projeto hospedado em:

```text
/EtherCraft/
```

---

# Evento Amigo Secreto

## CONFIRMADO — MÓDULO FUNCIONAL

O projeto começou originalmente como um site de evento de Amigo Secreto.

Esse sistema deve ser preservado para eventos futuros.

Características existentes:

* Steps 1 a 6.
* Validação do participante.
* Sorteio inteligente.
* Bloqueio contra auto-sorteio.
* Reserva global dos sorteados.
* Persistência via localStorage.
* Firebase/Firestore.
* Escolha entre oito opções visuais.
* Nome do item.
* Mensagem.
* Painel administrativo.
* Reset do evento.
* Tabela em tempo real.
* Status dos participantes.
* Interface administrativa.

A lógica funcional não deve ser alterada durante trabalhos exclusivamente visuais.

---

# Firebase

## CONFIRMADO

Firebase/Firestore é utilizado no sistema de eventos.

Coleções utilizadas no Amigo Secreto:

```text
participantes
usuarios
```

O frontend valida participantes antes de liberar o sorteio.

Documentos de usuários são criados através de `setDoc(..., { merge: true })` para evitar erro de atualização de documentos inexistentes.

---

# Painel Administrativo

Arquivos conhecidos:

```text
admin/
├── painel.html
├── painel.js
├── reset-evento.html
└── reset.js
```

Funções:

* Login ADM.
* Visualização da tabela.
* Atualização em tempo real.
* Copiar tabela.
* Resetar evento.
* Voltar ao site principal.

---

# Estrutura Atual do Projeto

## MAPA DE REFERÊNCIA

```text
EtherCraft
│
├── index.html
│
├── pages/
│   ├── regras.html
│   ├── eventos.html
│   ├── login.html
│   └── como-jogar.html
│
├── assets/
│   ├── images/
│   │   ├── Ether_Logo.png
│   │   ├── backgrounds/
│   │   └── eventos/
│   │       └── amigo-secreto/
│   ├── icons/
│   │   ├── android-chrome-192x192.png
│   │   ├── android-chrome-512x512.png
│   │   ├── apple-touch-icon.png
│   │   ├── favicon-16x16.png
│   │   ├── favicon-32x32.png
│   │   ├── favicon.ico
│   │   └── site.webmanifest
│   └── fonts/
│
├── css/
│   ├── reset.css
│   ├── base.css
│   ├── components.css
│   └── pages/
│       ├── home.css
│       ├── generic.css
│       ├── regras.css
│       ├── eventos.css
│       └── login.css
│
├── js/
│   ├── main.js
│   ├── firebase.js
│   └── modules/
│       └── amigo-secreto/
│           ├── index.html
│           ├── app.js
│           └── style.css
│
├── data/
│   └── participantes.json
│
└── admin/
    ├── painel.html
    ├── painel.js
    ├── reset-evento.html
    └── reset.js
```

---

# Regras de Continuidade

1. O repositório `mrserluiz/EtherCraft` é a fonte de verdade para o estado técnico atual do site.

2. Antes de grandes alterações, verificar os arquivos existentes no GitHub.

3. Não substituir funcionalidades funcionando sem necessidade.

4. Diferenciar claramente:

   * `CONFIRMADO`
   * `EM DESENVOLVIMENTO`
   * `PLANEJADO`
   * `NÃO IMPLEMENTADO`

5. A memória é cumulativa.

6. Updates futuros devem acrescentar histórico em vez de apagar decisões anteriores.

7. Alterações visuais não devem quebrar sistemas funcionais.

8. Todo update importante deve terminar com o mapa atualizado do site para confirmar alinhamento estrutural.

---

# Estado Atual

**STATUS:** EM DESENVOLVIMENTO

## CONFIRMADO

* Home funcional.
* GitHub Pages ativo.
* CSS modular.
* Navegação global.
* Design roxo/medieval.
* Responsividade.
* Fade da logo na Home.
* Favicons/PWA estruturados.
* Amigo Secreto funcional.
* Painel administrativo funcional.
* Firebase integrado.

## EM DESENVOLVIMENTO

* `pages/regras.html`
* `pages/eventos.html`
* Layout genérico das páginas internas.
* Organização definitiva de CSS específico das páginas.

## PRÓXIMA ETAPA

Consolidar o padrão visual das páginas internas sem alterar o visual já aprovado da Home.

Prioridades:

1. Definir `generic.css`.
2. Finalizar `regras.css`.
3. Finalizar página Eventos.
4. Garantir consistência da navegação.
5. Preservar responsividade e SEO.
