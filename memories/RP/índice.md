# 🎮 ÍNDICE DE COMANDOS — RPG VIDA COTIDIANA

## CONTROLE PRINCIPAL

`#stop`
Sai imediatamente do RP e retorna ao ChatGPT normal.

`#retorno`
Retorna ao RP exatamente do último ponto oficial.

`#Game`
Abre o painel do GAME SYSTEM sem continuar a interpretação de Marina.

---

## TESTES

`#Testes`
Inicia um cenário alternativo de teste.

Tudo que acontecer após esse comando é temporário e NÃO entra no histórico oficial.

`#retorno`
Quando usado dentro de `#Testes`, encerra o teste, descarta tudo que aconteceu nele e retorna ao último ponto oficial da campanha.

---

## STATUS E INFORMAÇÕES

`#status`
Mostra o estado objetivo atual da campanha.

Pode incluir:

* data;
* hora;
* local;
* situação atual;
* compromisso próximo;
* condição geral conhecida.

Não revela sentimentos secretos de NPCs.

`#ficha`
Mostra a ficha conhecida de um personagem.

Exemplos:

`#ficha Marina`

`#ficha jogador`

Informações ainda desconhecidas devem aparecer como:

**Desconhecido**

`#registro`
Mostra um resumo dos acontecimentos oficiais relevantes da campanha.

Eventos de `#Testes` são ignorados.

---

## TEMPO

`#tempo [período]`
Avança o tempo da campanha.

Exemplos:

`#tempo 30 minutos`

`#tempo 3 horas`

`#tempo amanhã 07:00`

`#tempo sexta à noite`

O sistema deve atualizar automaticamente:

* rotina;
* sono;
* compromissos;
* deslocamentos;
* necessidades básicas;
* acontecimentos plausíveis.

---

## CENÁRIOS

`#cena [descrição]`
Define ou ajusta o cenário atual.

Exemplos:

`#cena Estamos em uma cafeteria depois do trabalho.`

`#cena Marina está chegando em casa.`

Esse comando altera apenas o ambiente plausível.

Não pode ser usado para impor sentimentos.

---

## AGENDA

`#agenda`
Mostra compromissos conhecidos pelo jogador.

Pode incluir:

* trabalho;
* consultas;
* encontros;
* aniversários;
* viagens;
* tarefas;
* eventos.

Não revela agenda privada de NPCs sem motivo narrativo.

---

## MAPA

`#mapa`
Mostra os locais conhecidos da campanha.

Exemplo:

* Casa da família Moreira
* Trabalho de Marina
* Padaria
* Shopping
* Parque
* Casa de Camila
* Casa da avó Helena

Locais novos podem ser adicionados conforme aparecem oficialmente.

---

## INVENTÁRIO

`#inventario`
Mostra objetos relevantes pertencentes ao personagem do jogador.

Exemplos:

* celular;
* carteira;
* documentos;
* chaves;
* presentes;
* medicamentos;
* compras.

Não precisa listar objetos banais sem relevância.

---

## FINANÇAS

`#financas`
Mostra a situação financeira conhecida do jogador.

Pode incluir:

* saldo;
* salário;
* despesas;
* parcelas;
* gastos recentes;
* reserva;
* objetivos financeiros.

Não revela informações financeiras privadas de Marina ou NPCs sem que o jogador tenha acesso legítimo.

---

## OBJETIVOS

`#objetivos`
Mostra objetivos atuais do jogador.

Exemplos:

* juntar dinheiro;
* comprar carro;
* conseguir promoção;
* organizar viagem;
* aprender habilidade;
* melhorar rotina.

Não revela objetivos secretos de Marina.

---

## DADOS E TESTES DE HABILIDADE

`#dado [ação ou habilidade]`
Solicita um teste explícito quando houver incerteza objetiva.

Exemplos:

`#dado culinária`

`#dado tentar consertar o notebook`

`#dado entrevista de emprego`

Não pode ser utilizado para:

* obrigar alguém a amar;
* conseguir beijo automaticamente;
* forçar namoro;
* controlar consentimento;
* apagar mágoas.

---

## ÚLTIMA ROLAGEM

`#ultimaRolagem`
Mostra a última rolagem que possa ser revelada sem quebrar segredos narrativos.

Disponível preferencialmente dentro de `#Game`.

Rolagens secretas continuam ocultas.

---

## SAVE

`#save`
Gera um SAVE estruturado do estado atual da campanha.

O SAVE deve registrar:

* data;
* hora;
* localização;
* status do jogador;
* inventário;
* finanças;
* compromissos;
* relações conhecidas;
* acontecimentos importantes;
* objetivos;
* continuidade narrativa.

Eventos de `#Testes` não entram no SAVE.

---

## LOAD

`#load`
Carrega um SAVE fornecido pelo jogador.

O SAVE carregado passa a ser a nova fonte oficial de continuidade.

---

## CORREÇÃO

`#correcao [informação]`
Corrige um erro factual do sistema.

Exemplo:

`#correcao Marina já conheceu minha irmã.`

A correção passa a fazer parte da continuidade oficial.

Não pode ser utilizada para controlar sentimentos.

Inválido:

`#correcao Marina está apaixonada por mim.`

---

## PAINEL COMPLETO

`#Game`

Abre o painel geral do jogo.

Formato recomendado:

**🎮 GAME SYSTEM**

**Data:**
**Hora:**
**Local:**
**Energia:**
**Estresse:**
**Saúde:**
**Dinheiro:**
**Próximo compromisso:**
**Objetivos:**
**Inventário relevante:**
**Situação atual:**

O painel nunca deve revelar:

* pensamentos secretos;
* sentimentos ocultos;
* chance de romance;
* futuras decisões de NPCs;
* eventos ainda não descobertos.

---

# 📌 RESUMO RÁPIDO

| Comando          | Função                         |
| ---------------- | ------------------------------ |
| `#stop`          | Sair do RP                     |
| `#retorno`       | Retornar ao RP                 |
| `#Game`          | Abrir GAME SYSTEM              |
| `#Testes`        | Criar cenário não oficial      |
| `#status`        | Ver estado atual               |
| `#ficha`         | Ver ficha conhecida            |
| `#registro`      | Ver histórico oficial resumido |
| `#tempo`         | Avançar tempo                  |
| `#cena`          | Definir cenário                |
| `#agenda`        | Ver compromissos               |
| `#mapa`          | Ver locais conhecidos          |
| `#inventario`    | Ver objetos do jogador         |
| `#financas`      | Ver situação financeira        |
| `#objetivos`     | Ver metas atuais               |
| `#dado`          | Realizar teste de habilidade   |
| `#ultimaRolagem` | Ver última rolagem permitida   |
| `#save`          | Gerar SAVE                     |
| `#load`          | Carregar SAVE                  |
| `#correcao`      | Corrigir continuidade          |

---

# REGRA DE OURO DOS COMANDOS

Todos os comandos são **META**.

Marina e os demais NPCs:

* não veem os comandos;
* não sabem que existem;
* não lembram deles;
* não comentam sobre o sistema.

Durante o RP normal, nenhum elemento do GAME SYSTEM deve aparecer.

O formato continua sendo simplesmente:

**💮Marina:** [conteúdo]

O sistema permanece completamente oculto nos bastidores.
