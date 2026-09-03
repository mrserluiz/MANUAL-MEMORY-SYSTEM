================================
UPDATES:
========

UPDATE > 02/09/26 - 19:56 - M001A

# GOLDEN POT PROJECT — INICIALIZAÇÃO DO PROJETO

## OBJETIVO

Criar uma ferramenta complementar ao Rainbow responsável por comparar:

* o resource pack Bedrock principal e cumulativo do EtherTexture;
* uma nova saída Bedrock gerada pelo Rainbow;
* os custom mappings principais do Geyser;
* os novos custom mappings gerados pelo Rainbow.

O Golden Pot deve identificar somente conteúdos novos ou alterados e gerar uma nova versão atualizada do pacote principal sem destruir registros, arquivos ou estruturas já existentes.

O projeto nasce a partir do problema identificado durante a integração entre:

* EtherTexture;
* Rainbow;
* Geyser;
* CraftEngine;
* resource packs Java e Bedrock.

O Rainbow consegue converter novos conteúdos, porém uma nova varredura/conversão não necessariamente reproduz todo o histórico acumulado anteriormente.

Portanto, substituir diretamente o pacote ou os mappings principais por uma nova saída Rainbow pode causar regressões.

O Golden Pot deverá resolver esse problema utilizando atualização incremental.

---

## NOME DO PROJETO

Nome oficial:

`Golden Pot`

Origem do nome:

Referência ao “pote de ouro no fim do arco-íris”.

Rainbow gera a nova conversão.

Golden Pot coleta o conteúdo novo e incorpora ao pacote acumulativo.

---

## REPOSITÓRIO OFICIAL

Repositório oficial de desenvolvimento:

`https://github.com/mrserluiz/Golden_Pot_Poject`

Este repositório será considerado a fonte de verdade do código-fonte, arquitetura e releases do Golden Pot.

---

## MEMÓRIA DO PROJETO

Arquivo de memória:

`memories/Golden_Pot_Poject.md`

Repositório de memória:

`https://github.com/mrserluiz/MANUAL-MEMORY-SYSTEM`

A memória Golden Pot deve permanecer isolada de outros projetos, exceto quando houver dependência explicitamente registrada.

Dependências atualmente reconhecidas:

* EtherTexture;
* Rainbow;
* Geyser;
* CraftEngine.

Essas dependências não tornam suas memórias automaticamente parte do Golden Pot.

---

# PROBLEMA QUE ORIGINOU O GOLDEN POT

Durante a atualização do EtherTexture foi comparado:

```text
resourcepacks/EtherTexture Bedrock
```

com:

```text
resourcepacks/pack.testes.craft_engine
```

O primeiro representa o pacote Bedrock principal acumulativo.

O segundo representa uma nova saída criada pelo Rainbow depois da integração com CraftEngine.

Foi confirmado que a nova saída Rainbow:

* contém assets novos;
* contém novos mappings;
* contém novos modelos;
* contém novas animações;
* contém attachables novos;
* contém render controllers novos;

PORÉM:

também deixa de reproduzir alguns conteúdos existentes anteriormente no EtherTexture principal.

Logo:

```text
RAINBOW OUTPUT NOVO
!=
ESTADO COMPLETO DO ETHER TEXTURE
```

---

# PRINCÍPIO FUNDAMENTAL

Golden Pot não deve reconstruir o pacote principal do zero.

Golden Pot deve realizar:

```text
PRINCIPAL
+
NOVIDADES
-
DUPLICATAS
=
NOVO PRINCIPAL
```

Em outras palavras:

```text
Existing Pack
        +
Rainbow Output
        ↓
Golden Pot
        ↓
Merged Updated Pack
```

---

# REGRA DE SEGURANÇA

O Golden Pot NÃO deve editar destrutivamente o pacote original por padrão.

Fluxo desejado:

```text
PACK PRINCIPAL
        +
RAINBOW OUTPUT
        ↓
ANÁLISE
        ↓
PREVIEW
        ↓
MERGE
        ↓
NOVO OUTPUT
```

Exemplo:

```text
output/
└── EtherTexture-Bedrock-UPDATED/
```

O pacote original deve permanecer intacto até que a nova versão seja validada.

---

# CLASSIFICAÇÃO DE ARQUIVOS

Durante uma comparação, cada arquivo deverá receber um status.

Estados iniciais:

```text
ADDED
UNCHANGED
MODIFIED
CONFLICT
PROTECTED
REMOVED
```

Tradução funcional:

### ADDED

Arquivo existe somente na nova saída Rainbow.

Ação provável:

copiar para o novo pacote.

---

### UNCHANGED

Arquivo existe nos dois pacotes e é idêntico.

Detecção preferencial:

hash.

Ação:

nenhuma.

---

### MODIFIED

Mesmo caminho existe nos dois pacotes, porém o conteúdo é diferente.

Ação depende do tipo de arquivo e das regras configuradas.

---

### CONFLICT

Golden Pot não consegue determinar de forma segura qual conteúdo deve prevalecer.

Ação:

não sobrescrever automaticamente.

Exibir conflito para decisão.

---

### PROTECTED

Arquivo ou caminho explicitamente protegido.

Exemplo:

```text
textures/block/crop/
manifest.json
```

Ação:

não substituir automaticamente.

---

### REMOVED

Arquivo existe no principal, mas não aparece na nova conversão Rainbow.

IMPORTANTE:

ausência no novo Rainbow NÃO significa que o arquivo deve ser removido.

Por padrão:

```text
REMOVED → PRESERVAR
```

---

# COMPARAÇÃO DE ARQUIVOS

Arquivos binários e arquivos individuais deverão inicialmente ser comparados por:

```text
relative path
+
hash
```

Possível algoritmo:

```text
mesmo caminho + mesmo hash
→ UNCHANGED

novo caminho
→ ADDED

mesmo caminho + hash diferente
→ MODIFIED

somente no principal
→ PRESERVE
```

---

# JSONS ESPECIAIS

Alguns arquivos NÃO podem ser tratados como arquivos comuns.

Eles exigem merge estrutural.

Arquivos inicialmente reconhecidos:

```text
geyser_item_mappings.json
item_texture.json
terrain_texture.json
```

Possíveis arquivos futuros:

```text
geyser_block_mappings.json
geyser_skull_mappings.json
geyser_waypoint_style_mappings.json
```

---

# GEYSER ITEM MAPPINGS

Arquivo:

```text
geyser_item_mappings.json
```

Regra:

O arquivo principal é cumulativo.

Uma nova saída Rainbow é considerada fonte de novos registros, e não substituta integral do principal.

Exemplo:

Principal:

```json
"minecraft:echo_shard": [
  { "bedrock_identifier": "ether:item/ruby" },
  { "bedrock_identifier": "ether:item/sapphire" }
]
```

Novo Rainbow:

```json
"minecraft:echo_shard": [
  { "bedrock_identifier": "ether:item/new_gem" }
]
```

Resultado esperado:

```json
"minecraft:echo_shard": [
  { "bedrock_identifier": "ether:item/ruby" },
  { "bedrock_identifier": "ether:item/sapphire" },
  { "bedrock_identifier": "ether:item/new_gem" }
]
```

Regra:

```text
não duplicar
não apagar
adicionar novidades
```

---

# ITEM TEXTURE ATLAS

Arquivo:

```text
textures/item_texture.json
```

Golden Pot deverá comparar:

```text
texture_data
```

e preservar registros existentes.

Fluxo:

```text
texture_data PRINCIPAL
        +
texture_data NOVO
        ↓
MERGE
```

Se uma chave não existir:

```text
ADICIONAR
```

Se existir com exatamente o mesmo valor:

```text
UNCHANGED
```

Se existir com valor diferente:

```text
CONFLICT ou MODIFIED
```

Nunca apagar registros do principal simplesmente porque não aparecem na nova saída.

---

# TERRAIN TEXTURE ATLAS

Arquivo:

```text
textures/terrain_texture.json
```

Mesma estratégia de merge incremental.

Motivo:

o EtherTexture possui atualmente mappings de crops já testados e funcionando no Bedrock.

Uma nova conversão do Rainbow pode gerar versões diferentes desses arquivos.

Portanto, uma execução futura não deve sobrescrever automaticamente registros validados.

---

# CAMINHOS PROTEGIDOS INICIAIS

Primeira proposta:

```text
manifest.json
textures/block/crop/
```

Possibilidade de configuração futura:

```json
{
  "protected_paths": [
    "manifest.json",
    "textures/block/crop/"
  ]
}
```

---

# MANIFEST

O `manifest.json` principal representa a identidade do resource pack Bedrock.

Uma nova saída Rainbow normalmente recebe:

* novo nome;
* novo UUID;
* nova versão;
* novo module UUID.

Golden Pot não deverá substituir automaticamente o manifest principal.

Possível comportamento futuro:

```text
preservar UUID
preservar identidade
incrementar version
```

---

# ARQUITETURA INICIAL PROPOSTA

```text
GoldenPot/
│
├── scanner/
│   ├── PackScanner
│   └── HashComparator
│
├── merger/
│   ├── FileMerger
│   ├── GeyserItemMappingMerger
│   ├── ItemTextureMerger
│   └── TerrainTextureMerger
│
├── rules/
│   └── protected-paths.json
│
├── reports/
│
├── output/
│
└── ui/
```

Esta arquitetura ainda é PROPOSTA e pode mudar durante o desenvolvimento.

---

# FLUXO DE USO DESEJADO

Interface conceitual:

```text
Golden Pot
│
├── Principal Pack:
│   [ selecionar pasta ]
│
├── Rainbow Output:
│   [ selecionar pasta ]
│
├── Principal Mappings:
│   [ selecionar pasta ]
│
├── Rainbow Mappings:
│   [ selecionar pasta ]
│
└── [ ANALISAR ]
```

Resultado:

```text
New files: 74
Unchanged: 29
Modified: 4
Conflicts: 2
Protected: 12
```

Depois:

```text
[ GERAR NOVO PACK ]
```

---

# RELATÓRIO

Cada execução deve idealmente gerar um relatório.

Exemplo:

```text
Golden Pot Merge Report

ADDED: 74
UNCHANGED: 29
MODIFIED: 4
MERGED JSON ENTRIES: 41
CONFLICTS: 2
PROTECTED: 12
REMOVED: 0
```

Objetivo:

permitir auditoria e reversibilidade.

---

# VERSÕES PLANEJADAS

## V0.1 — Comparator

Objetivo:

comparar dois packs sem alterar nenhum arquivo.

Funções:

```text
scan de diretórios
comparação por caminho
hash dos arquivos
classificação de diferenças
relatório
```

Status:

`NÃO IMPLEMENTADO`

---

## V0.2 — Merge Engine

Objetivo:

gerar uma nova pasta combinada.

Funções previstas:

```text
copiar ADDED
preservar UNCHANGED
não apagar arquivos antigos
proteger paths
detectar conflitos
```

JSONs prioritários:

```text
geyser_item_mappings.json
item_texture.json
terrain_texture.json
```

Status:

`NÃO IMPLEMENTADO`

---

## V0.3 — Rainbow Integration

Objetivo:

avaliar integração mais direta com o Rainbow.

Possibilidades:

```text
ferramenta companion
addon
fork
biblioteca compartilhada
integração via output
```

Nenhuma abordagem está confirmada ainda.

Status:

`NÃO IMPLEMENTADO`

---

## V1.0 — Golden Pot

Objetivo final:

ferramenta utilizável para atualização incremental do EtherTexture Bedrock e mappings do Geyser.

Fluxo:

```text
Rainbow
   ↓
Golden Pot
   ↓
EtherTexture atualizado
```

Status:

`PLANEJADO`

---

# RELAÇÃO COM O RAINBOW

Golden Pot não pretende inicialmente substituir o Rainbow.

Rainbow permanece responsável pela conversão:

```text
Java
→
Bedrock/Geyser
```

Golden Pot será inicialmente responsável por:

```text
Rainbow Output
+
Existing Bedrock Pack
→
Safe Incremental Merge
```

Isso reduz significativamente a necessidade de realizar novamente varreduras manuais de todo o catálogo.

---

# RELAÇÃO COM ETHERTEXTURE

EtherTexture continua sendo o pacote acumulativo principal.

Golden Pot funciona como ferramenta de manutenção/atualização.

Conceito:

```text
EtherTexture
      ↑
Golden Pot
      ↑
Rainbow
```

---

# RELAÇÃO COM CRAFTENGINE

CraftEngine pode gerar novos:

* custom items;
* custom blocks;
* furniture;
* equipment;
* modelos;
* resource packs Java.

Rainbow converte esses conteúdos para Bedrock/Geyser.

Golden Pot deverá então detectar o que essa nova conversão adicionou e mesclar somente as novidades no EtherTexture acumulativo.

---

# DESCOBERTAS QUE MOTIVARAM O PROJETO

Durante uma comparação real foi observado:

A principal `EtherTexture Bedrock` continha assets antigos válidos que não estavam presentes na nova saída Rainbow.

Ao mesmo tempo, a nova saída continha:

```text
render_controllers/
novas animations
novos attachables
novos models
textures/block/custom/
textures/entity/
textures/item/custom/
```

Portanto:

substituição integral = risco.

Merge incremental = estratégia desejada.

---

# PRINCÍPIO DE DESENVOLVIMENTO

Golden Pot deve priorizar:

```text
PRESERVAÇÃO
PREVISIBILIDADE
REVERSIBILIDADE
AUDITORIA
```

Antes de automação agressiva.

Quando houver dúvida:

```text
não sobrescrever
→ reportar conflito
```

---

# ESTADO ATUAL

## CONFIRMADO

* Nome do projeto: Golden Pot.
* Repositório oficial definido.
* Arquivo de memória definido.
* Problema técnico que originou o projeto confirmado.
* EtherTexture será tratado como estado principal acumulativo.
* Rainbow Output será tratado como fonte de novidades.
* Merge deverá ser incremental.
* Arquivos antigos não devem ser apagados por ausência em uma nova conversão.
* JSONs agregadores exigem merge semântico.
* Manifest deve ser protegido inicialmente.
* Saída deve preferencialmente ser gerada em nova pasta.
* Comparação por caminho + hash é adequada para a primeira versão.

## NÃO IMPLEMENTADO

* Código do Golden Pot.
* Linguagem de programação final.
* Interface gráfica.
* CLI.
* Algoritmo completo de conflito.
* Integração direta com Rainbow.
* Cache persistente.
* Sistema de plugins/addons.
* Build/release.

---

# PRÓXIMO PASSO

Definir o escopo técnico do:

```text
Golden Pot v0.1
```

e escolher:

```text
linguagem
estrutura do repositório
formato de configuração
algoritmo de scan
algoritmo de hash
formato do relatório
CLI ou GUI inicial
```

A primeira versão deverá apenas analisar e reportar diferenças, sem modificar os arquivos originais.

<END UPDATE>

==================================================
GOLDEN POT PROJECT / Golden_Pot_Poject
======================================

Criada em 02/09/26 - 19:56

Projeto complementar ao Rainbow para atualização incremental, segura e cumulativa de resource packs Bedrock e custom mappings do Geyser.

SOURCE OF TRUTH:

`https://github.com/mrserluiz/Golden_Pot_Poject`

MEMORY:

`memories/Golden_Pot_Poject.md`

DEPENDÊNCIAS EXPLÍCITAS:

* Rainbow
* Geyser
* EtherTexture
* CraftEngine

OBJETIVO CENTRAL:

```text
PACK PRINCIPAL
+
NOVA SAÍDA RAINBOW
↓
GOLDEN POT
↓
NOVO PACK ATUALIZADO
```

Regra fundamental:

**preservar o conteúdo acumulado e incorporar somente novidades ou alterações deliberadamente aprovadas.**

==================================================

