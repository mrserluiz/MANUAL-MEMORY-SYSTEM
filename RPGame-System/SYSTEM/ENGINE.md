# Motor documental de RPG — v0.1
## Escopo
Regras independentes de mundo para operar o RPG por leitura e atualização destes arquivos. O GitHub mantém a versão persistida; mudanças em conversa permanecem propostas até serem salvas.

## Inicialização
1. Selecionar explicitamente um mundo; nunca misturar personagens, objetos ou memórias entre mundos.
2. Ler WORLD, CANON, TIMELINE e CURRENT-STATE do mundo.
3. Recuperar fichas, memórias, relações, lugares e itens relevantes à cena.
4. Conferir fase de importação, lacunas e contradições. Se o ponto de parada estiver desconhecido, continuar a reconstrução, sem criar uma cena de retomada.

## Ciclo de sessão
1. Recuperar contexto relevante e identificar presentes, local, tempo, posse de objetos e conhecimento de cada participante.
2. Conferir continuidade antes de narrar; consultar fonte quando faltar evidência.
3. O jogador determina suas ações e falas. Narrador controla mundo e NPCs.
4. Após a cena, propor somente mudanças sustentadas pelo que ocorreu: eventos, memórias, relações, itens e estado.
5. Validar que transferências têm origem/destino, memórias têm meios de aquisição e cronologia não contradiz eventos estabelecidos.
6. Persistir sessão e arquivos afetados juntos em um commit. Informar se a gravação falhar; nunca dizer que salvou sem confirmação.

## Comandos convencionados
- #continuar: retomar a partir do estado validado.
- #inventário: consultar posse confirmada; desconhecido não significa vazio.
- #personagem NOME: consultar ficha.
- #memórias NOME: consultar registro individual, fora da narrativa.
- #relações, #resumo, #timeline: consultar registros relevantes.
- #salvar: preparar e persistir mudanças da sessão conforme autorização.
- #voltar cena: propor uma revisão com indicação do ponto de retorno; preservar o histórico e reconciliar todas as consequências.

Estes comandos são convenções para o narrador, não funções de software já implementadas.
