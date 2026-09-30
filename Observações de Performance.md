# Observações de performance

Pontos de investigação levantados durante o QA. Usar IDs sequenciais e medir antes de atribuir causas ou recomendar otimizações.

## PERF-001 — Tempo de login e carregamento inicial

- **Data:** 30/09/2026.
- **Status:** análise pendente; duração e gargalo ainda não medidos.
- **Solicitação:** analisar a performance de entrada no jogo.

### Referência

A captura mostra a tela de carregamento com a mensagem “Içando as velas...”. Não comprova quanto tempo essa etapa leva nem se há travamento.

![Tela de carregamento inicial](evidencias/PERF-001-login-carregamento.png)

### O que medir

- Tempo entre iniciar o login e ter o jogo pronto para interação; separar autenticação, carregamento dos dados do jogador, download de recursos e inicialização da cena.
- Comparar primeiro acesso com cache vazio e acessos seguintes com cache, em várias tentativas.
- Registrar versão do jogo, navegador, dispositivo, condições de rede e erros encontrados.
- Usar medições de rede e perfil de performance do navegador para identificar requisições lentas, recursos pesados e tarefas que bloqueiam a interface.

### Critério de análise

Identificar qual etapa concentra a espera e definir uma meta de tempo com base nas medições. Verificar também se a barra representa progresso real e se falhas exibem uma mensagem útil em vez de deixar o jogador esperando indefinidamente.

Após um ajuste, repetir as mesmas condições e comparar o tempo até o jogo estar utilizável, sem antecipar o fim do carregamento antes de os recursos necessários estarem prontos.
