# ==================================================

# HYDRAXIA_REBUILD

# ==================================================

# ================================ UPDATES:

UPDATE > 05/10/26 - 20:00 - M001A

## IDENTIFICAÇÃO DO PROJETO

Projeto: recuperação/rebuild do Community Pack **Hydraxia** para utilização através do **Terra2.0**.

Repositórios principais:

* Hydraxia:
  https://github.com/Jaddotish/Hydraxia

* Terra2.0:
  https://github.com/mrserluiz/Terra2.0

* TerraOverworldConfig:
  https://github.com/PolyhedralDev/TerraOverworldConfig

* Tartarus:
  https://github.com/PolyhedralDev/Tartarus

Memória persistente deste projeto:

[https://github.com/mrserluiz/MANUAL-MEMORY-SYSTEM/blob/main/memories/Hydraxia_rebuild](https://github.com/mrserluiz/MANUAL-MEMORY-SYSTEM/blob/main/memories/Hydraxia_rebuild.md)

Fonte de verdade operacional:

**GitHub + histórico Git.**

A memória deste arquivo deve registrar decisões, descobertas, testes, erros, hipóteses, estado atual e próximos passos necessários para que uma nova instância possa continuar o trabalho sem reconstruir todo o histórico.

---

## 1. OBJETIVO PRINCIPAL

O objetivo NÃO é reescrever, simplificar ou modernizar conceitualmente o Hydraxia.

O objetivo é:

**RECUPERAR / FINALIZAR O HYDRAXIA ORIGINAL PARA QUE ELE POSSA SER UTILIZADO COMO COMMUNITY PACK ATRAVÉS DO TERRA2.0.**

A intenção inicial é preservar o conteúdo original do Hydraxia.

Não remover biomas, estruturas ou sistemas apenas por quantidade antes de determinar o que realmente impede sua execução.

O primeiro objetivo é obter uma versão funcional e fiel ao projeto original.

Somente depois de uma versão funcional existir deverá ser considerada uma variante otimizada/reduzida, caso testes demonstrem problemas reais de desempenho.

---

## 2. MODELO CONCEITUAL DEFINIDO

O Terra2.0 deve ser tratado como a camada de compatibilidade/execução moderna.

O Hydraxia continua sendo o Community Pack original.

Modelo:

Hydraxia original
↓
Terra2.0
↓
engine moderno
↓
Minecraft/Paper

Portanto, a prioridade não é alterar o Hydraxia para se parecer com o Terra2.0.

A prioridade é verificar:

1. quais partes do Hydraxia já são compreendidas pelo Terra2.0;
2. quais partes precisam de compatibilidade;
3. quais partes realmente estão quebradas;
4. quais problemas são apenas ausência de build/release;
5. quais alterações mínimas permitem produzir um artefato funcional.

---

## 3. ESTADO CONHECIDO DO HYDRAXIA

CONFIRMADO NO REPOSITÓRIO:

O repositório `Jaddotish/Hydraxia` existe publicamente.

Branch principal observado:

`master`

Histórico observado:

`24 commits`

Estrutura principal atual:

* `biome_distribution/`
* `biomes/`
* `features/`
* `functions/`
* `palettes/`
* `samplers/`
* `structures/`
* `LICENSE`
* `README.md`
* `pack.yml`

O README identifica o projeto como:

**Hydraxia: A Winterland's Fantasy**

Descrição original:

um pack de geração Terra que transforma o Overworld em um mundo de inverno permanente.

O README informa:

* compatibilidade histórica com Minecraft Java 1.19.2+;
* mais de 60 biomas;
* 29 biomas de caverna;
* utilização de geração de mundo Terra;
* forte relação com a configuração Overworld original do Terra;
* existência de estruturas/features/etc.;
* projeto originalmente marcado como Work In Progress/playtesting.

O próprio README informa que o Hydraxia utilizava partes/configurações derivadas do TerraOverworldConfig.

IMPORTANTE:

O README original também contém um aviso histórico de que o pack ainda estava em desenvolvimento e não deveria ser utilizado em produção.

Isso NÃO deve ser interpretado automaticamente como prova de que o pack atual é incompatível com Terra2.0.

Essa conclusão ainda precisa ser testada.

---

## 4. ESTADO CONHECIDO DO TERRA2.0

CONFIRMADO NO REPOSITÓRIO ATUAL:

O `mrserluiz/Terra2.0` existe publicamente.

Branch principal observado:

`main`

Histórico observado:

`142 commits`

O repositório contém, entre outros:

* `terra2-engine/`
* `terra2-plugin/`
* `addons/`
* `packs/`
* `ENGINE-MIGRATION.md`
* `BUILD-STATUS.md`
* documentação e artefatos de investigação.

O README atual descreve o Terra2.0 como uma continuação independente e orientada à segurança do engine Terra, em processo de modernização, mantendo compatibilidade com Community Packs.

O repositório também informa que a recuperação do engine ainda está em andamento.

### CONTEXTO EXPLICITAMENTE FORNECIDO PELO USUÁRIO

O usuário corrigiu uma interpretação anterior:

O Terra2.0 JÁ consegue gerar Community Packs.

Foram citados como exemplos funcionais:

* `PolyhedralDev/TerraOverworldConfig`
* `PolyhedralDev/Tartarus`

Portanto, NÃO considerar como estado atual a hipótese antiga de que Community Packs ainda não estavam validados.

Segundo o estado informado pelo usuário, os principais componentes ainda não concluídos do Terra2.0 são:

* datapack conversion;
* world/item management.

Essa informação deve ser tratada como contexto atual fornecido pelo usuário até ser confrontada com commits/documentação técnica mais específica.

---

## 5. DECISÃO FUNDAMENTAL DO PROJETO

Foi descartada a abordagem inicial de:

"pegar o Hydraxia e selecionar apenas alguns biomas para torná-lo mais leve".

Motivo:

O objetivo principal é recuperar o Hydraxia original.

O fato de o pack possuir mais de 60 biomas, incluindo 29 biomas de caverna, NÃO é por si só motivo suficiente para remover conteúdo.

A abordagem correta é:

### FASE 1 — HYDRAXIA CLASSIC

Recuperar o máximo possível do Hydraxia original.

Preservar:

* biomas;
* cave biomes;
* distribuição;
* features;
* estruturas;
* palettes;
* samplers;
* functions;
* configurações;
* identidade original do pack.

### FASE 2 — OTIMIZAÇÃO

Somente depois de existir uma versão funcional:

avaliar desempenho real.

Se necessário, criar futuramente:

**Hydraxia Lite**

com subconjunto selecionado de conteúdo.

Essa variante NÃO deve substituir a recuperação do Hydraxia original.

---

## 6. PAPEL DOS OUTROS COMMUNITY PACKS

`TerraOverworldConfig` e `Tartarus` devem ser utilizados como:

**REFERÊNCIAS DE COMPATIBILIDADE E FUNCIONAMENTO.**

Eles NÃO devem ser tratados como conteúdo a ser copiado para dentro do Hydraxia.

A finalidade da comparação é descobrir:

Hydraxia component
↓
Terra2.0 suporta?
↓
Overworld/Tartarus demonstram esse suporte?
↓
se não:
qual é o blocker?
↓
qual é a menor correção necessária?

Isso permite distinguir:

* problema do Hydraxia;
* problema do Terra2.0;
* diferença de versão;
* addon ausente;
* sintaxe incompatível;
* dependência não recuperada;
* artefato de build ausente.

---

## 7. PRINCÍPIO DE RECUPERAÇÃO

O trabalho deve seguir:

**Git history > memória/inferência.**

Não assumir que o último commit do Hydraxia é necessariamente a melhor versão.

É necessário reconstruir:

1. histórico dos commits;
2. evolução do pack;
3. alterações relevantes;
4. último estado conhecido como funcional;
5. alterações posteriores;
6. eventual regressão;
7. existência ou ausência de artefatos de distribuição;
8. dependências usadas por cada estado.

A pergunta central é:

> Qual commit representa o melhor estado funcional recuperável do Hydraxia e o que impede esse estado de ser utilizado hoje através do Terra2.0?

---

## 8. MATRIZ DE RECUPERAÇÃO PLANEJADA

A análise deverá produzir uma matriz semelhante a:

| Componente Hydraxia | Suporte Terra2.0 | Evidência                   | Estado   | Blocker  | Correção mínima |
| ------------------- | ---------------- | --------------------------- | -------- | -------- | --------------- |
| pack.yml            | a verificar      | Overworld/Tartarus + engine | PENDENTE | PENDENTE | PENDENTE        |
| biome_distribution  | a verificar      | packs funcionais            | PENDENTE | PENDENTE | PENDENTE        |
| biomes              | a verificar      | packs funcionais            | PENDENTE | PENDENTE | PENDENTE        |
| features            | a verificar      | packs funcionais            | PENDENTE | PENDENTE | PENDENTE        |
| functions           | a verificar      | engine/addons               | PENDENTE | PENDENTE | PENDENTE        |
| palettes            | a verificar      | packs funcionais            | PENDENTE | PENDENTE | PENDENTE        |
| samplers            | a verificar      | engine/addons               | PENDENTE | PENDENTE | PENDENTE        |
| structures          | a verificar      | engine/addons               | PENDENTE | PENDENTE | PENDENTE        |

Essa matriz deverá ser preenchida com evidências reais do código, configuração e testes.

---

## 9. CRITÉRIO DE "FUNCIONAL"

Para o primeiro milestone, Hydraxia funcional significa:

1. pack reconhecido pelo Terra2.0;
2. pack carregado sem erro fatal;
3. dependências resolvidas;
4. geração de mundo iniciada;
5. terreno gerado;
6. biomas sendo distribuídos;
7. features principais funcionando;
8. estruturas, quando suportadas, funcionando;
9. ausência de erros críticos recorrentes;
10. possibilidade de produzir um build/artefato utilizável.

Não é necessário considerar o pack "perfeito" para declarar o primeiro milestone atingido.

Bugs históricos de balanceamento ou problemas cosméticos podem ser registrados separadamente.

---

## 10. O QUE NÃO FAZER

Não:

* reescrever o Hydraxia inteiro;
* converter o pack para outro formato sem necessidade;
* remover os 60+ biomas como primeira solução;
* assumir que biomas de caverna são o problema;
* copiar conteúdo do TerraOverworldConfig para substituir Hydraxia;
* copiar conteúdo do Tartarus para substituir Hydraxia;
* alterar a identidade do pack;
* declarar incompatibilidade sem teste;
* declarar compatibilidade sem teste;
* tratar inferência como fato;
* criar uma release artificialmente baseada apenas em lembrança.

Qualquer alteração deverá ter uma razão técnica identificável.

---

## 11. HIPÓTESES AINDA NÃO CONFIRMADAS

As seguintes questões permanecem abertas e NÃO devem ser registradas como fatos:

* qual é exatamente o último commit funcional do Hydraxia;
* se o HEAD atual é funcional ou possui regressões;
* se a ausência de download/release é simplesmente ausência de artefato ou consequência de incompatibilidade;
* quais addons do Hydraxia já são completamente suportados pelo Terra2.0;
* quais recursos exigirão mudanças no engine;
* se structures precisam de recuperação adicional;
* se features específicas possuem incompatibilidades;
* se os 29 cave biomes apresentam algum problema real;
* qual será o impacto de desempenho do pack completo;
* se datapack conversion terá qualquer impacto no primeiro build funcional do Hydraxia.

Esses pontos precisam ser investigados.

---

## 12. ABORDAGENS DESCARTADAS

### Abordagem descartada: reduzir imediatamente o número de biomas

Motivo:

O objetivo inicial é recuperação fiel.

Performance deve ser medida, não presumida.

### Abordagem descartada: modernizar/reprojetar Hydraxia

Motivo:

O Terra2.0 deve fornecer a camada moderna de execução/compatibilidade.

O conteúdo original do Community Pack deve ser preservado.

### Abordagem descartada: considerar Terra2.0 incapaz de executar Community Packs

Motivo:

O usuário informou que Terra2.0 já consegue gerar Community Packs, incluindo TerraOverworldConfig e Tartarus.

O repositório atual também identifica explicitamente a compatibilidade com Community Packs como objetivo do projeto.

---

## 13. PRÓXIMA INVESTIGAÇÃO

A próxima etapa deve ser uma investigação técnica baseada em Git:

### Etapa A — Hydraxia

* listar os 24 commits;
* identificar commits de criação/evolução;
* identificar alterações de `pack.yml`;
* identificar alterações de addons;
* identificar mudanças de biome distribution;
* identificar mudanças de structures/features;
* procurar evidência de build/release;
* identificar o último estado plausivelmente funcional.

### Etapa B — Terra2.0

* identificar no histórico quando Community Packs passaram a funcionar;
* identificar o mecanismo usado para carregar/interpretar packs;
* identificar addons disponíveis;
* identificar limitações atuais;
* identificar qualquer documentação específica sobre packs.

### Etapa C — Comparação

Comparar Hydraxia com:

* TerraOverworldConfig;
* Tartarus.

Objetivo:

descobrir quais recursos Hydraxia utiliza que já possuem cobertura comprovada no Terra2.0.

### Etapa D — Primeiro teste

Selecionar o melhor commit recuperável do Hydraxia.

Executar:

Hydraxia commit X
↓
Terra2.0
↓
load
↓
generation test
↓
logs
↓
classificação dos erros

### Etapa E — Correção mínima

Corrigir somente os blockers comprovados.

Depois repetir o teste.

---

## 14. OBJETIVO DO PRIMEIRO MILESTONE

O primeiro resultado concreto esperado é:

**Hydraxia Classic — primeiro build funcional recuperado**

Não necessariamente uma release final.

O milestone deve permitir:

* instalar o pack;
* selecionar/ativar o pack através do Terra2.0;
* criar um mundo;
* gerar terreno;
* explorar os biomas;
* verificar caves/features/structures;
* coletar logs;
* registrar problemas restantes.

Depois disso poderá ser criada uma versão de distribuição propriamente dita.

---

## 15. ESTADO ATUAL DA MEMÓRIA

ACTIVE_PROJECT = `Hydraxia_rebuild`

ACTIVE_MEMORY = `memories/Hydraxia_rebuild`

ACTIVE_MODE = INACTIVE

ACTIVE_RP = INACTIVE

SOURCE_OF_TRUTH = GitHub

CURRENT_OBJECTIVE = Recuperar/finalizar Hydraxia original para Terra2.0

KNOWN_CONFLICTS = Existe histórico de interpretações anteriores incorretas sobre o estado do Terra2.0; a informação atual do usuário deve prevalecer para o contexto imediato e ser confrontada com o repositório quando necessário.

CURRENT_STATE = Planejamento e preparação da recuperação técnica.

NO_BUILD_TEST_PERFORMED_YET = TRUE

NO_HYDRAXIA_MODIFICATION_PERFORMED_YET = TRUE

NO_HYDRAXIA_BIOME_REMOVAL_APPROVED = TRUE

---

## 16. REGRA DE CONTINUIDADE

Qualquer nova instância que carregar esta memória deve:

1. consultar o GitHub antes de assumir estado técnico atual;
2. consultar o histórico Git quando a pergunta envolver evolução/regressão;
3. preservar a separação entre Hydraxia e Terra2.0;
4. utilizar TerraOverworldConfig e Tartarus como referências de compatibilidade;
5. não remover conteúdo do Hydraxia sem decisão explícita;
6. distinguir CONFIRMADO de NÃO CONFIRMADO;
7. registrar testes e resultados;
8. atualizar esta memória somente através de novos UPDATEs;
9. nunca apagar histórico anterior sem autorização;
10. continuar pelo próximo passo pendente em vez de reiniciar a investigação.

================================================== <END UPDATE>

