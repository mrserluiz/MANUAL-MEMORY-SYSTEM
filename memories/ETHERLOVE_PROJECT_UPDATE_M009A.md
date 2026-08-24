UPDATE > 23/08/2026 - 22:20 - M009A
ETHERLOVE REBUILD 001 — RELATIONSHIPID FIX / UX / CASE 6 / ADMIN TOOLS
==========================================================

STATUS
==========================================================

Durante o primeiro teste real no servidor foi identificado um
bug crítico na simetria do RelationshipID.

Sintoma observado:

PLAYER1 executa:
/RP PLAYER2
→ +10 XP

PLAYER2 executa:
/RP PLAYER1
→ deveria resultar em 20 XP na mesma relação

Porém o relacionamento continuava exibindo apenas 10 XP.

A causa provável foi confirmada no Core:

a função etherIDFromUUIDs() utilizava comparação genérica
"is less than" para ordenar UUIDs em formato texto.

Isso podia produzir chaves inconsistentes dependendo da ordem
do executor/alvo.

==========================================================
1. CORREÇÃO CRÍTICA — RELATIONSHIP ID
==========================================================

Arquivo alterado:

EtherLove/00-etherlove-core.sk

Nova revisão:

CORE REVISION 006 — CANONICAL RELATIONSHIP ID

Commit:

fe85db0cf49906c4ecf071285d5a8a4d7fc5dc1d

A ordenação passou a utilizar:

alphabetically sorted %texts%

Modelo atual:

function etherIDFromUUIDs(uuid1: text, uuid2: text) :: text:
    set {_uuids::*} to {_uuid1} and {_uuid2}
    set {_sorted::*} to alphabetically sorted {_uuids::*}
    return "%{_sorted::1}%::%{_sorted::2}%"

REGRA OBRIGATÓRIA:

PLAYER1 + PLAYER2
=
PLAYER2 + PLAYER1

sempre devem retornar exatamente a mesma RelationshipID.

==========================================================
2. IMPORTANTE — DADOS DE TESTE ANTIGOS
==========================================================

Relações criadas antes da Revision 006 podem ter sido
armazenadas em duas chaves diferentes.

Portanto os dados usados durante o primeiro teste não devem
ser considerados confiáveis para validar soma de XP após a
correção.

Para novo teste:

- usar uma dupla sem dados anteriores;
OU
- limpar/resetar os dados antigos de teste.

Uma ferramenta administrativa de limpeza/migração poderá ser
criada posteriormente se necessário.

==========================================================
3. CASE CONTINUA SENDO CONTROLE INTERNO
==========================================================

Nova decisão de UX:

O termo CASE deve permanecer como controle interno do
EtherLove.

Jogadores não devem visualizar principalmente:

CASE 0
CASE 1
CASE 2
...

A interface deve usar os nomes amigáveis dos estágios:

0 = NEUTRO
1 = AMIGO
2 = MELHORES AMIGOS
3 = PAIXAO
4 = NAMORANDO
5 = NOIVOS
6 = CASADOS

Exemplo de feedback desejado:

Estado: NEUTRO
XP: 020/500

em vez de:

CASE atual: 0

==========================================================
4. NOVO MENU /LOVE
==========================================================

Será criado um menu oficial de relacionamentos:

/LOVE

O menu deve mostrar uma entrada para cada relação conhecida
do jogador.

Nome da entrada:

<PLAYER1> & <PLAYER2>

Lore:

Estado: <NOME DO ESTÁGIO>
XP: 010/500

Formato de XP preferido:

000/500
010/500
095/500
100/500
500/500

==========================================================
5. ÍCONES DO MENU /LOVE
==========================================================

Mapa visual definido:

CASE 0 / NEUTRO
→ LÃ BRANCA

CASE 1 / AMIGO
→ LÃ AZUL-CLARA

CASE 2 / MELHORES AMIGOS
→ LÃ AZUL

CASE 3 / PAIXAO
→ LÃ ROSA

CASE 4 / NAMORANDO
→ LÃ MAGENTA / LILÁS

CASE 5 / NOIVOS
→ LÃ VERMELHA

CASE 6 / CASADOS
→ BLOCO DE MINÉRIO DE OURO

==========================================================
6. CUSTOM MODEL DATA DO MENU
==========================================================

As entradas do /LOVE devem já nascer preparadas para futura
textura customizada por Resource Pack.

Planejamento de CMD reservado:

NEUTRO            → 8100
AMIGO             → 8101
MELHORES AMIGOS   → 8102
PAIXAO            → 8103
NAMORANDO          → 8104
NOIVOS             → 8105
CASADOS            → 8106

STATUS:

PLANNED / NOT IMPLEMENTED YET

==========================================================
7. INDEXAÇÃO DE RELACIONAMENTOS PARA /LOVE
==========================================================

O protótipo antigo do menu percorre apenas jogadores online.

Isso não é suficiente.

O Core deverá futuramente manter um índice persistente das
relações de cada UUID para que /LOVE consiga mostrar relações
mesmo quando o outro jogador estiver offline.

Conceito planejado:

{etherlove.player.%UUID%.relationships::*}

A relação poderá também armazenar:

uuid-a
uuid-b
name-a
name-b

O menu continuará sendo apenas VIEW.

Não duplicar XP/CASE/STATUS na interface.

==========================================================
8. CASE 6 — /TPC
==========================================================

Novo comando confirmado para CASADOS:

/TPC

Não necessita argumento.

O sistema já conhece o cônjuge através do Active Partner Index.

Requisitos:

CASE = 6
STATUS = CASADO
cônjuge online
vínculo ativo consistente

Efeito:

quem executa /TPC chama/teleporta o cônjuge até sua posição.

==========================================================
9. CASE 6 — /OBAOBA <PLAYER>
==========================================================

Comando confirmado:

/OBAOBA <player2>

Requisitos:

- relação entre executor e alvo deve ser CASE 6;
- STATUS = CASADO;
- alvo deve ser o cônjuge ativo;
- os dois precisam estar próximos de uma cama;
- PLAYER2 deve aceitar via /LS;
- /LN recusa sem penalidade.

Ao aceitar, as condições devem ser verificadas novamente.

Se ainda válidas:

PLAYER1
+
PLAYER2

recebem:

REGENERAÇÃO por 3 minutos.

CASE 6 não utiliza XP.

Planejamento inicial para proximidade de cama:

raio de aproximadamente 3 blocos para cada jogador.

Esse valor pode ser ajustado em teste.

O Pending Action System deverá receber:

OBAOBA_REQUEST

==========================================================
10. ADMIN — /LADD XP
==========================================================

Novo comando administrativo planejado:

/LADD <PLAYER1> <PLAYER2> <VALOR>

Objetivo:

adicionar ou remover XP diretamente de uma relação para
administração/debug.

Exemplos:

/LADD P1 P2 50
→ +50 XP

/LADD P1 P2 -50
→ -50 XP

Deve recalcular CASE/STATUS pelas APIs normais do Core,
respeitando a arquitetura do relacionamento.

Permissão administrativa será definida na implementação.

==========================================================
11. ADMIN — CERIMONIALISTA
==========================================================

Comando solicitado:

/LADD <PLAYER> C

Objetivo:

conceder ao jogador a permissão:

etherlove.ceremonialist

Assim o jogador poderá executar as funções de Cerimonialista
sem necessidade de OP.

Como LuckPerms já faz parte do ambiente do servidor, a
implementação preferida é conceder a permission real através
do LuckPerms em vez de criar uma tag paralela.

Também é recomendado criar futuramente:

/LREMOVE <PLAYER> C

para remover a função.

==========================================================
12. ADMIN — DEBUG COMPLETO
==========================================================

Planejado:

/LDEBUG <PLAYER1> <PLAYER2>

Deve mostrar pelo menos:

- nomes;
- UUIDs;
- RelationshipID;
- XP;
- CASE RAW;
- nome do estágio;
- STATUS;
- Active Partner de cada jogador;
- Pending Action de cada jogador;
- DATE ativo;
- Mailbox ocupada/vazia;
- created;
- last-interaction.

Esse comando será a principal ferramenta de diagnóstico do
EtherLove durante os testes no servidor.

==========================================================
13. PRÓXIMA ORDEM DE DESENVOLVIMENTO
==========================================================

1. VALIDAR Revision 006 no servidor:

P1 /RP P2
+
P2 /RP P1
=
20 XP na MESMA relação.

2. Depois implementar:

02 INTERACTIONS REVISION
→ mostrar nomes de estágio em vez de CASE ao jogador.

3. CORE / INDEX UPDATE
→ índice persistente de relações para /LOVE.

4. 04 INTERFACE REBUILD
→ /LOVE
→ cores por estágio
→ lore
→ XP 000/500
→ CustomModelData reservado.

5. CASE 6 ACTIONS
→ /TPC
→ /OBAOBA

6. ADMIN TOOLS
→ /LADD P1 P2 XP
→ /LADD PLAYER C
→ /LDEBUG P1 P2

==========================================================
14. ESTADO ATUAL
==========================================================

CORE REVISION 006
✅ RELATIONSHIP ID CANÔNICO IMPLEMENTADO

BUG P1↔P2 DUPLICADO
✅ CORRIGIDO NO CÓDIGO
⏳ AGUARDANDO RETESTE NO SERVIDOR

/LOVE
🟡 DEFINIDO / NÃO IMPLEMENTADO

/TPC
🟡 DEFINIDO / NÃO IMPLEMENTADO

/OBAOBA
🟡 DEFINIDO / NÃO IMPLEMENTADO

/LADD
🟡 DEFINIDO / NÃO IMPLEMENTADO

/LDEBUG
🟡 DEFINIDO / NÃO IMPLEMENTADO

==========================================================
FIM DO UPDATE M009A
==========================================================
