# UPDATE — ETHERCRAFT SITE
## Firebase, Perfil, Área Administrativa, Wiki + Firestore e próximos passos visuais
### Data: 16/09/2026

---

# 1. OBJETIVO ATUAL

O site EtherCraft evoluiu da fase de autenticação básica para uma estrutura funcional com:

- Firebase Authentication;
- perfis persistentes via Firestore;
- sistema de roles;
- área administrativa;
- listagem de usuários;
- Wiki conectada ao Firestore;
- CRUD administrativo da Wiki;
- preparação para upload de imagens via Cloudinary;
- nova direção visual da Wiki baseada em livros temáticos.

O repositório principal continua sendo:

`https://github.com/mrserluiz/EtherCraft`

Hospedagem:

`https://mrserluiz.github.io/EtherCraft/`

---

# 2. FIREBASE — ESTADO ATUAL

Projeto Firebase:

`EtherCraft`

Project ID:

`ethercraft-378c3`

Authentication:

- Email/Password ✅
- Cadastro ✅
- Login ✅
- Logout ✅
- Recuperação de senha ✅
- Verificação de e-mail ✅
- Persistência de sessão ✅
- Domínio `mrserluiz.github.io` autorizado ✅

Firebase JS SDK utilizado:

`12.18.0`

`js/firebase.js` inicializa:

- Firebase App;
- Authentication;
- persistência local;
- Cloud Firestore.

---

# 3. FIRESTORE — IMPLEMENTADO E FUNCIONAL

A antiga etapa planejada de Firestore foi concluída.

Estrutura usada:

```text
usuarios/
  {uid}/
    nome
    email
    minecraftNick
    avatar
    role
    favoritos
    recentes
    criadoEm
```

Fluxo:

```text
Firebase Authentication
        ↓
       UID
        ↓
Firestore
usuarios/{uid}
```

Ao abrir o perfil:

- se o documento já existe, é lido normalmente;
- se não existe, é criado automaticamente;
- dados antigos locais podem ser migrados para o Firestore.

O usuário testou a sincronização entre sessões/dispositivos e confirmou que os dados reapareceram corretamente.

Portanto:

Firestore perfil persistente:
✅ FUNCIONANDO

Sincronização entre sessões:
✅ FUNCIONANDO

---

# 4. ROLES E SEGURANÇA

Roles atuais utilizadas:

```text
player
admin
```

A conta administrativa foi promovida manualmente pelo Firebase Console para:

```text
role: "admin"
```

A intenção é impedir que o próprio cliente eleve permissões.

Security Rules publicadas com lógica de:

- jogador lê o próprio perfil;
- admin pode ler qualquer perfil;
- jogador pode editar o próprio perfil sem alterar `role`;
- admin pode editar qualquer usuário;
- admin pode excluir documentos de usuários;
- conteúdo da Wiki pode ser lido publicamente;
- somente admin pode criar/editar/excluir conteúdo da Wiki.

Princípio obrigatório:

Nunca confiar apenas em JavaScript para segurança de cargo.

A autorização real deve permanecer nas Firestore Security Rules.

---

# 5. PERFIL DO JOGADOR — ESTADO ATUAL

Página:

`pages/perfil.html`

Script:

`js/profile.js`

Funcionalidades:

- avatar;
- nome de exibição;
- nome Minecraft;
- e-mail;
- status de verificação;
- edição do perfil;
- logout;
- favoritos;
- páginas recentes;
- progresso de eventos visual;
- leitura do `role` via Firestore.

O sistema de avatar continua fechado:

- emojis oficiais;
- futuramente PNGs oficiais;
- não permitir foto externa arbitrária por URL.

Correções anteriores do avatar continuam válidas:

- linha horizontal removida;
- centralização corrigida;
- hover `Editar foto` funcionando;
- modal centralizado.

---

# 6. PERFIL ADMIN — VISUAL

Quando o Firestore retorna:

```text
role: "admin"
```

o perfil muda visualmente.

Regras atuais:

- nome do perfil fica verde;
- aparece botão `Área Administrativa`;
- botão fica no canto superior direito do card inteiro do perfil;
- posicionamento absoluto;
- não altera o tamanho do card.

O usuário enviou uma referência visual marcando a área desejada e confirmou depois:

`perfeito`

Portanto a posição atual do botão ADM deve ser preservada.

---

# 7. ÁREA ADMINISTRATIVA

Página criada:

`pages/admin.html`

Script:

`js/admin.js`

A área administrativa atualmente possui:

- validação de sessão;
- validação de `role == admin`;
- redirecionamento para perfil se não for admin;
- leitura da coleção `usuarios`;
- listagem dos usuários;
- tabela com:
  - Nome no Minecraft;
  - Nome de exibição;
  - Cargo;
- contador de usuários;
- destaque visual para Admin.

Objetivo futuro:

expandir a área ADM para ferramentas adicionais, inclusive gestão da Wiki.

---

# 8. MENU E NAVEGAÇÃO GLOBAL

Ordem oficial:

```text
Home
Eventos
Regras
Como Jogar
Wiki
Login / Perfil
```

Regras:

- `Wiki` sempre penúltimo;
- `Login / Perfil` sempre último;
- deslogado → `Login`;
- logado → `Perfil`.

`js/main.js` faz atualização dinâmica da conta e sessão.

Correções já confirmadas:

- `pages/regras.html` usa caminho correto para `../js/main.js`;
- `pages/eventos.html` usa caminho correto;
- navegação das páginas foi ajustada;
- páginas internas da Wiki devem usar `../../js/...`.

---

# 9. SESSÃO

Persistência local do Firebase está ativa.

Política própria de inatividade:

`12 horas`

Com atividade do usuário:

- sessão permanece.

Após longa inatividade:

- logout automático.

Logout manual também permanece disponível.

---

# 10. FAVORITOS E RECENTES

Anteriormente eram apenas locais.

Agora a estrutura Firestore do perfil possui:

```text
favoritos
recentes
```

A integração atual usa esses campos no perfil persistente.

O site também mantém chaves locais como fallback/cache durante a transição.

Status:

Favoritos:
✅ ESTRUTURA FIRESTORE

Recentes:
✅ ESTRUTURA FIRESTORE

Sincronização principal de perfil:
✅ CONFIRMADA

---

# 11. PROGRESSO DE EVENTOS

Seção visual existe no perfil:

`🏆 Progresso de eventos`

Estado:

Interface:
✅ EXISTE

Dados reais de eventos:
❌ AINDA NÃO IMPLEMENTADOS

Integração com eventos:
❌ AINDA NÃO IMPLEMENTADA

Não interpretar o `0%` atual como progresso real.

---

# 12. WIKI — ESTRUTURA DE PÁGINAS

Página inicial:

`pages/wiki.html`

Categorias:

```text
pages/wiki/
├── mecanicas.html
├── receitas.html
├── bestiario.html
├── dimensoes.html
├── encantamentos.html
└── economia.html
```

Dados antigos estáticos ainda existem em:

```text
data/wiki/
├── mecanicas.json
├── receitas.json
├── mobs.json
├── dimensoes.json
├── encantamentos.json
└── economia.json
```

Esses JSONs agora funcionam como fonte inicial/fallback, não como destino definitivo de publicação.

---

# 13. WIKI + FIRESTORE — IMPLEMENTADO

Arquivo criado:

`js/wiki-firestore.js`

Responsabilidades:

- conectar a Wiki ao Firestore;
- ler conteúdo por categoria;
- gravar conteúdo;
- excluir conteúdo;
- verificar role atual;
- importar automaticamente JSON inicial quando a coleção está vazia e o usuário é Admin.

Estrutura Firestore:

```text
wiki/
  receitas/
    entries/{id}
  mobs/
    entries/{id}
  encantamentos/
    entries/{id}
  dimensoes/
    entries/{id}
  economia/
    entries/{id}
  mecanicas/
    entries/{id}
```

A Wiki usa:

```text
wiki/{categoria}/entries/{id}
```

Security Rules:

- leitura pública;
- escrita apenas por admin.

---

# 14. MIGRAÇÃO JSON → FIRESTORE

Lógica atual:

```text
abrir categoria
      ↓
Firestore verifica entries
      ↓
se vazio + usuário admin
      ↓
carrega data/wiki/*.json
      ↓
cria documentos no Firestore
```

Se Firestore estiver indisponível:

- a página tenta carregar o JSON local como fallback.

Portanto o design/conteúdo não deve simplesmente desaparecer por falha de backend.

---

# 15. CRUD ADMINISTRATIVO DA WIKI

`js/wiki-content.js` foi atualizado.

Admin atualmente pode visualizar controles:

```text
[ + Adicionar ]
[ ✏️ Editar ]
[ 🗑️ Excluir ]
```

Jogador comum:

- não vê esses controles.

A detecção de admin foi reforçada:

- lê estado global da autenticação;
- também consulta o role via Firestore.

Excluir:

- exige confirmação antes de apagar;
- chama Firestore;
- remove o conteúdo da interface após sucesso.

Salvar:

- grava diretamente no Firestore;
- alteração passa a ser global para todos os visitantes.

Arquivos envolvidos:

```text
js/wiki-content.js
js/wiki-firestore.js
css/pages/wiki-content.css
```

---

# 16. WIKI — DESIGN VISUAL ATUAL VS NOVA DIREÇÃO

IMPORTANTE:

O usuário enviou novas referências visuais em 16/09/2026.

As alterações feitas até aqui na Wiki foram principalmente FUNCIONAIS.

O usuário informou:

`não vejo as alterações visuais no site`

Isso é esperado porque a integração Firestore/CRUD ainda preserva majoritariamente a estrutura visual anterior.

Nova decisão visual:

## Página inicial da Wiki

Usar um livro genérico como identidade visual inicial.

Referência enviada como:

`Imagem 1`

## Categorias da Wiki

Usar um novo fundo/base de livro aberto para:

- Bestiário;
- Receitas;
- Encantamentos;
- Dimensões;
- Economia;
- Mecânicas.

Referência enviada como:

`Imagem 5`

A ideia é que o Firestore apenas forneça os dados.

O design de livro deve permanecer como camada visual independente.

---

# 17. RESPONSIVIDADE DO NOVO LIVRO

No desktop:

```text
┌──────────────────────────────────────┐
│          LIVRO ABERTO               │
│                                      │
│ página esquerda | página direita     │
│                                      │
└──────────────────────────────────────┘
```

No mobile:

NÃO encolher o livro inteiro até o texto ficar ilegível.

A experiência desejada é separar visualmente:

```text
[PÁGINA ESQUERDA]
       ↓
 próxima
       ↓
[PÁGINA DIREITA]
```

Ou mecanismo equivalente de paginação/folheio.

A referência mobile foi enviada pelo usuário.

---

# 18. FONTE MINECRAFT

O usuário enviou:

`minecraft.zip`

O ZIP contém uma fonte para uso nos elementos temáticos dos livros.

Arquivo citado:

`Minecraft.ttf`

Direção de uso:

- títulos de livros;
- capítulos;
- elementos visuais Minecraft;
- partes futuras do site quando fizer sentido.

NÃO aplicar indiscriminadamente a todo o site.

Texto comum deve preservar legibilidade.

Planejamento de estrutura:

```text
assets/fonts/Minecraft.ttf
```

IMPORTANTE:

não compartilhar externamente o arquivo de fonte.

---

# 19. CLOUDINARY — NOVA ETAPA

O usuário quer armazenar as imagens da Wiki no Cloudinary.

Objetivo:

```text
Admin escolhe imagem
      ↓
Cloudinary
      ↓
URL segura
      ↓
Firestore salva URL
      ↓
Wiki renderiza imagem
```

Tipos previstos:

- imagem de mob;
- ícone de drop;
- ingredientes de receita;
- resultado de receita;
- imagem de encantamento;
- ícones de equipamentos;
- imagem de dimensão;
- imagem de mecânica;
- imagens de economia.

Não salvar binários diretamente no Firestore.

Firestore deve guardar apenas URLs e metadados.

---

# 20. CLOUDINARY — ACESSO E UPLOAD PRESET

Foi discutida a criação de:

`Unsigned Upload Preset`

Nome sugerido:

`ethercraft_wiki`

Configuração planejada:

```text
Signing mode: Unsigned
Asset folder: EtherCraft/Wiki
Allowed formats: png, webp, jpg, jpeg
Unique filename: ON
Disallow public ID: ON
```

Nunca colocar no frontend:

- Cloudinary API Secret;
- senha;
- credenciais privadas.

Cloud name e preset unsigned podem ser usados pelo cliente.

O usuário informou que em outra instância consegue trabalhar no Cloudinary pelo navegador suspenso / Cloud Browser do ChatGPT Work.

Decisão:

Ao mudar de instância, usar Work/Cloud Browser para operar diretamente o Cloudinary e configurar tudo de uma vez.

Esta conversa NÃO possui o mesmo acesso de navegador da outra instância.

---

# 21. PRÓXIMO FLUXO RECOMENDADO NA NOVA INSTÂNCIA

Objetivo: fazer a próxima fase em bloco, evitando pequenos remendos separados.

Sequência recomendada:

1. Abrir o Cloudinary via Work/Cloud Browser.
2. Criar/verificar `Unsigned Upload Preset`.
3. Organizar pasta de assets da Wiki.
4. Definir `cloud_name` e `upload_preset` no frontend, sem segredo.
5. Criar upload direto pelo painel ADM da Wiki.
6. Salvar URLs no Firestore.
7. Integrar upload aos campos do editor da Wiki.
8. Adicionar a fonte Minecraft ao projeto.
9. Aplicar o novo visual de livro da Imagem 5 às categorias.
10. Manter Imagem 1 como direção visual da entrada da Wiki.
11. Criar comportamento mobile página esquerda → página direita.
12. Testar CRUD completo:

```text
Admin
 ↓
Adicionar conteúdo
 ↓
Upload imagem
 ↓
Cloudinary
 ↓
URL
 ↓
Firestore
 ↓
Wiki pública
```

---

# 22. COMMITS IMPORTANTES DESTA FASE

Perfil ADM / botão área administrativa:

```text
9e876aace6f6e8bf7472e5490c6a55c10a0af019
c2a84bd3af70d7fcf6630cad330e4ccb0136444e
```

Área administrativa:

```text
55e27ddccc56ecda743a202fe1d0c270d44afa27
b841c5d204d46c42db4b930682e1cc0b42e4adc7
```

Botão do perfil apontando para Admin:

```text
4a201c030d00ad9859eedbda70661c94381d6de8
```

Wiki + Firestore:

```text
88f3bf5c1f151c566cf999dd327116080cf20a91
e06884e859d5b5f43d766c1f1670657e773610dc
```

Atualizações das páginas da Wiki para nova integração:

```text
074f7aa791bb7b23304d5cf225952503e7cc5c16
ca4caa14957264e0fdadd709b198c12a0d3a6f53
73c68c881de95ccccee77f4f3aff9053971f4d96
af9c4d9c4fc3bbda2af8dc697d1c8f59a60961d3
23d3c5828df166614f3c7c851a9fd8d096a6d2b4
fd4be27f31cd03e3e3cd9062b8e5fb095c5c4db9
```

CRUD / delete / reconhecimento de Admin na Wiki:

```text
408884dfa5564dc350ba0bb800f521be2f976a23
f7a290b1653c08c4c13b786e1ea7651587b0f7f2
```

---

# 23. REGRAS DE PATHS DO GITHUB PAGES

Manter:

## Root

```text
index.html
```

usar:

```text
pages/...
js/...
css/...
```

## Dentro de `/pages/`

usar:

```text
../index.html
../js/...
../css/...
```

## Dentro de `/pages/wiki/`

usar:

```text
../../index.html
../../js/...
../../css/...
../../data/...
```

A pasta correta é minúscula:

`pages/`

GitHub Pages é case-sensitive.

---

# 24. ARQUIVOS PRINCIPAIS ATUAIS

```text
EtherCraft
│
├── index.html
│
├── pages/
│   ├── login.html
│   ├── perfil.html
│   ├── admin.html
│   ├── eventos.html
│   ├── regras.html
│   ├── wiki.html
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
│   ├── auth.js
│   ├── profile.js
│   ├── admin.js
│   ├── main.js
│   ├── wiki.js
│   ├── wiki-content.js
│   ├── wiki-firestore.js
│   └── wiki-motion.js
│
├── css/
│   ├── reset.css
│   ├── base.css
│   ├── components.css
│   └── pages/
│       ├── wiki.css
│       ├── wiki-content.css
│       └── wiki-motion.css
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
│   ├── images/
│   │   └── wiki/
│   │       ├── livro-inicial        ← PLANEJADO / referência enviada
│   │       └── livro-categoria      ← PLANEJADO / referência enviada
│   └── fonts/
│       └── Minecraft.ttf            ← ARQUIVO ENVIADO / AINDA INTEGRAR
│
└── Firebase EtherCraft
    ├── Authentication              ✅
    ├── Firestore usuarios          ✅
    ├── Roles                       ✅
    ├── Rules administrativas       ✅
    └── Wiki Firestore              ✅ estrutura/código
```

---

# 25. ESTADO ATUAL CONSOLIDADO

## CONFIRMADO / FUNCIONAL

Authentication:
✅

Perfil persistente:
✅

Firestore usuários:
✅

Sincronização entre sessões:
✅

Role `admin`:
✅

Security Rules administrativas:
✅ PUBLICADAS

Nome verde para Admin:
✅

Botão Área Administrativa:
✅ posição aprovada

Página Admin:
✅

Tabela de usuários:
✅

Listagem de nick Minecraft:
✅

Wiki com Firestore:
✅ CÓDIGO IMPLEMENTADO

CRUD Admin da Wiki:
✅ CÓDIGO IMPLEMENTADO

Leitura pública da Wiki via Rules:
✅ LIBERADA

JSON fallback:
✅

## AINDA PRECISA DE TESTE / FINALIZAÇÃO

Migração de todas as categorias para Firestore:
🟡 TESTAR categoria por categoria

Edição real de entrada e recarregamento:
🟡 TESTAR

Exclusão real:
🟡 TESTAR

Upload de imagens Cloudinary:
❌ AINDA NÃO IMPLEMENTADO

Unsigned Upload Preset:
❌ AINDA NÃO CONFIGURADO NESTA INSTÂNCIA

Novo visual de livro das categorias:
❌ AINDA NÃO IMPLEMENTADO

Fonte Minecraft no GitHub:
❌ AINDA NÃO INTEGRADA

Responsividade livro página esquerda/direita:
❌ AINDA NÃO IMPLEMENTADA

Progresso real de eventos:
❌ NÃO IMPLEMENTADO

---

# 26. DECISÕES IMPORTANTES PARA CONTINUIDADE

1. Não redesenhar a Wiki apenas por causa do Firestore.
2. Firestore é camada de dados; livro é camada visual.
3. Jogadores comuns não veem ferramentas ADM.
4. Admin pode adicionar, editar e excluir conteúdo.
5. Segurança real deve permanecer nas Rules.
6. Imagens da Wiki devem ir para Cloudinary; Firestore guarda URL.
7. Não colocar API Secret do Cloudinary no frontend.
8. Fonte Minecraft deve ser usada de forma temática, não global.
9. Desktop usa livro aberto com duas páginas.
10. Mobile deve apresentar as páginas separadamente em sequência/paginação, e não simplesmente encolher tudo.
11. A entrada da Wiki usa direção visual do livro genérico enviado como Imagem 1.
12. Categorias usam o novo fundo de livro enviado como Imagem 5.
13. Preservar design já aprovado do restante do site.
14. Continuar compatível com GitHub Pages.
15. Sempre verificar arquivos atuais no repositório antes de grandes alterações.

---

# 27. PRÓXIMA ETAPA NA NOVA INSTÂNCIA

Abrir o projeto em uma instância com **Work / Cloud Browser** disponível para operar o Cloudinary diretamente.

Começar por:

```text
Cloudinary
├── configurar/verificar unsigned upload preset
├── organizar EtherCraft/Wiki
└── obter cloud_name + preset público
```

Depois continuar no GitHub:

```text
Wiki
├── upload direto de imagem pelo editor ADM
├── URL salva no Firestore
├── integração da Minecraft.ttf
├── novo visual dos livros
└── mobile em páginas separadas
```

---

# STATUS FINAL DESTE UPDATE

```text
AUTHENTICATION              ✅ FUNCIONAL
PERFIL                      ✅ FUNCIONAL
FIRESTORE PERFIL            ✅ FUNCIONAL
ROLE ADMIN                  ✅ FUNCIONAL
RULES ADMIN                 ✅ PUBLICADAS
ÁREA ADMINISTRATIVA         ✅ FUNCIONAL
LISTA DE USUÁRIOS           ✅ FUNCIONAL
WIKI FIRESTORE              ✅ IMPLEMENTADO EM CÓDIGO
WIKI CRUD ADMIN             ✅ IMPLEMENTADO EM CÓDIGO
WIKI VISUAL NOVO            ❌ PENDENTE
CLOUDINARY                  ❌ PENDENTE NESTA INSTÂNCIA
MINECRAFT.TTF               🟡 ARQUIVO ENVIADO / PENDENTE INTEGRAÇÃO
PROGRESSO DE EVENTOS        ❌ PENDENTE
```

# MAPA FINAL PARA CONTINUIDADE

```text
EtherCraft
│
├── Site principal
│   ├── Home
│   ├── Eventos
│   ├── Regras
│   ├── Login
│   ├── Perfil
│   └── Área Administrativa
│
├── Conta
│   ├── Firebase Authentication
│   ├── Firestore usuarios/{uid}
│   ├── roles player/admin
│   └── sessão 12h
│
├── Wiki
│   ├── Entrada visual em livro
│   ├── Mecânicas
│   ├── Receitas
│   ├── Bestiário
│   ├── Dimensões
│   ├── Encantamentos
│   └── Economia
│
├── Backend
│   ├── usuarios/{uid}
│   └── wiki/{categoria}/entries/{id}
│
├── Administração Wiki
│   ├── + Adicionar
│   ├── Editar
│   └── Excluir
│
└── Próxima fase
    ├── Cloudinary
    ├── upload de imagens
    ├── Minecraft.ttf
    ├── novo fundo de livro
    └── mobile página esquerda → direita
```
