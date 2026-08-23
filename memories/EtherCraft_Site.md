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
