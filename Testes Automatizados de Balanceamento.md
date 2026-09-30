# Testes automatizados de balanceamento

## Ideia

Criar uma ferramenta interna que simule combates e permita a um agente testar combinações de equipamentos, atributos, buffs, efeitos e alvos. O objetivo é detectar quando uma alteração aparentemente pequena — como aumentar um atributo em 5% — gera um impacto muito maior no endgame.

Esse sistema é independente da proposta de configuração de munições e pode avaliar qualquer mecânica de combate.

## Como funcionaria

1. O simulador reutiliza as mesmas regras de combate do jogo, sem precisar renderizar a partida no Babylon.js.
2. O orquestrador executa cenários com builds válidas, respeitando slots, requisitos, incompatibilidades e orçamento.
3. O agente explora combinações, procura interações fortes e transforma os resultados em casos reproduzíveis.
4. Cada mudança é comparada com a versão anterior usando os mesmos cenários e sementes de aleatoriedade.
5. Um relatório mostra o impacto e sinaliza resultados fora das faixas esperadas.

## O que testar

- Início, meio e principalmente endgame, com builds comuns e otimizadas.
- PvE e PvP, alvo único e grupos, combates curtos e prolongados.
- Diferentes defesas, resistências, imunidades e quantidades de vida.
- Acúmulo e reaplicação de efeitos, chances de ativação e combinações de bônus.
- Casos extremos: cadência alta, crítico elevado, redução de recarga e controle contínuo.

Medir dano por segundo, dano em janelas curtas, tempo para matar, sobrevivência e tempo sob controle. Separar as fontes de dano e, quando aplicável, medir taxa de vitória e custo por combate.

## Exemplo: aumento de 5%

Ao aumentar um atributo em 5%, executar as versões anterior e nova nas mesmas condições. Verificar se alguma build passou a matar com um ataque a menos, ativar efeitos com mais frequência, ultrapassar um limite ou manter o adversário sem reação.

O ganho real pode ser desproporcional por causa de multiplicadores, arredondamentos, limites e mudanças na quantidade de ações. O relatório deve mostrar onde isso aconteceu, qual combinação causou o resultado e como reproduzi-lo.

## Papel do agente

O agente usa o simulador para procurar builds fortes como um jogador experiente faria. Pode começar com builds conhecidas e busca aleatória, ampliando a busca conforme o conteúdo crescer.

Para cada problema encontrado, entrega:

- Build e cenário usados, sementes e versões dos dados e regras.
- Resultado antes e depois, com variação estatística quando houver aleatoriedade.
- Interações responsáveis pelo ganho e limitações da busca.

Descrever o resultado como **melhor build encontrada**, sem presumir que todas as combinações foram exploradas. O agente recomenda investigação; a decisão de balanceamento continua com o desenvolvedor.

## Alertas e implementação inicial

Definir faixas por cenário e etapa de progressão. Alertar sobre tempo para matar muito baixo, controle sem oportunidade de reação, efeitos ativados além do esperado ou uma opção dominando situações demais. Um alerta é um indício para investigar, não uma prova automática de desbalanceamento.

Começar com um núcleo compartilhado de combate, cenários fixos, builds de referência e um relatório antes/depois. Rodar essa bateria a cada alteração de balanceamento e guardar casos problemáticos como testes de regressão. Depois, adicionar a busca automática do agente.

As simulações complementam testes humanos: posicionamento, habilidade dos jogadores e economia também influenciam o resultado real.
