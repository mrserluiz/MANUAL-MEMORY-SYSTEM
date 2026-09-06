# MEMÓRIA DO PROJETO — EXBR SITE

**ID da memória:** `#EXBR_Site`  
**Arquivo:** `memories/EXBR_Site.md`  
**Criado em:** 06/09/2026  
**Última atualização:** 06/09/2026  
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
