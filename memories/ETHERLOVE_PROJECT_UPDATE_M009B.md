# ETHERLOVE PROJECT — UPDATE M009B

**Data:** 2026-09-01

## Objetivo
Registrar a implementação dos itens posteriores à correção canônica do RelationshipID.

## IMPLEMENTADO

### Display de estados
CASE permanece exclusivamente como controle interno.
Interface ao jogador usa:
- 0 = NEUTRO
- 1 = AMIGO
- 2 = MELHORES AMIGOS
- 3 = PAIXAO
- 4 = NAMORANDO
- 5 = NOIVO
- 6 = CASADO

`02-etherlove-interactions.sk` atualizado para exibir Estado em vez de CASE.

### /LOVE
`04-etherlove-interface.sk` reconstruído.
GUI de relacionamentos com ícones:
- NEUTRO = lã branca / CMD 8100
- AMIGO = lã azul-clara / CMD 8101
- MELHORES AMIGOS = lã azul / CMD 8102
- PAIXAO = lã rosa / CMD 8103
- NAMORANDO = lã magenta / CMD 8104
- NOIVO = lã vermelha / CMD 8105
- CASADO = minério de ouro / CMD 8106

Lore mostra Estado e XP no formato 000/500.
`/EL` mantido temporariamente como alias de `/LOVE`.

### 03D Married Actions
Novo arquivo `03d-etherlove-married-actions.sk`.

`/TPC`:
- exclusivo para CASE6/STATUS CASADO;
- usa Active Partner Index;
- cônjuge precisa estar online;
- teleporta o cônjuge até quem executou o comando.

`/OBAOBA <player>`:
- exclusivo para cônjuges CASADOS;
- ambos devem estar a até 3 blocos de uma cama;
- cria Pending Action `OBAOBA_REQUEST`;
- `/LS` aceita e `/LN` recusa;
- condições são revalidadas no aceite;
- aceite aplica Regeneração por 3 minutos aos dois;
- não altera XP.

### 05 Admin Tools
Novo arquivo `05-etherlove-admin.sk`.

`/LADD <player1> <player2> <valor>`:
- adiciona ou remove XP para debug;
- cria relação se necessário;
- respeita congelamento de XP do CASE6.

`/LADD <player> C`:
- concede `etherlove.ceremonialist` via LuckPerms;
- permite atuar como Cerimonialista sem OP.

`/LDEBUG <player1> <player2>`:
- mostra RelationshipID, UUIDs, XP, CASE RAW, Estado, STATUS, Active Partner, Pending Action, DATE e mailbox.

`/LRESET <player1> <player2>`:
- ferramenta de teste/recuperação;
- remove as duas possíveis chaves antigas UUID1::UUID2 e UUID2::UUID1;
- limpa Active Partner/Pending;
- recria relação canônica em NEUTRO / 0 XP.

## IMPORTANTE
O RelationshipID canônico da Revision 006 continua sendo a regra obrigatória para todos os módulos.

## PENDENTE / TESTE NO SERVIDOR
- Validar parser de CustomModelData no `/LOVE` na versão instalada do Skript.
- Validar detecção genérica de camas no 03D.
- Validar interceptação de `/LS` e `/LN` para `OBAOBA_REQUEST`.
- Testar `/LADD <player> C` contra a versão instalada do LuckPerms.
- O `/LOVE` atual lista relações encontradas entre jogadores online; índice persistente de todas as relações/offline ainda pode ser adicionado em revisão futura.
