# Sugestões de features

Ideias levantadas durante o QA para avaliação do desenvolvedor. Não representam bugs confirmados nem funcionalidades cuja ausência já foi verificada. Usar IDs sequenciais para novas sugestões.

## FEAT-001 — NPCs com perfis de atributos diferentes

**Status:** sugestão para avaliação de balanceamento.

Além das habilidades especiais, variar um pouco os atributos de alguns NPCs: mais defesa, redução de dano ou resistência a críticos, por exemplo. Pode ser aplicado a mapas mais altos, novos NPCs e expansões, ou aos conteúdos existentes durante o desenvolvimento.

**Objetivo:** aproveitar a variedade de itens para incentivar builds pensadas para cada situação, com vantagens e contrapartidas, em vez de uma única combinação ser a melhor em todo lugar.

**Exemplos:** builds com mais perfuração contra inimigos cuja defesa seja afetada por esse atributo; builds com foco em crítico onde ele seja eficiente; outras fontes de dano contra inimigos resistentes a críticos.

**Ponto a validar:** perfuração só deve ser apresentada como resposta à redução de dano se as regras do jogo permitirem essa interação. Da mesma forma, mais dano crítico pode compensar anticrítico ou ter pouco valor, dependendo de o anticrítico reduzir a chance, o dano ou impedir críticos. Conferir as fórmulas antes de definir essas especializações.

Evitar apenas aumentar a resistência de todos os inimigos. Os perfis devem criar escolhas perceptíveis, com informações suficientes para o jogador entender e adaptar a build.

## FEAT-002 — Canhões com cadências e danos base distintos

**Status:** sugestão para avaliação de balanceamento.

Criar canhões com diferenças de comportamento: um ataca mais rápido, mas causa menos dano por disparo; outro causa mais dano por disparo, mas tem recarga maior.

**Benefício:** ampliar as opções de build e a escolha entre dano contínuo e ataques mais fortes. Avaliar também a interação com críticos, efeitos por acerto e outros bônus, pois cadência maior pode gerar vantagens além do DPS base.

## FEAT-003 — Validar o limite de velocidade de ataque

**Status:** verificação pendente; não confirmado como bug ou recurso ausente.

Verificar se existe um intervalo mínimo entre ataques, equivalente a um limite máximo de velocidade de ataque, mesmo ao combinar itens e buffs de redução de recarga.

**Objetivo:** evitar ataques quase instantâneos e spam de acertos no endgame. Testar combinações extremas no sistema de testes automatizados de balanceamento, incluindo efeitos ativados por acerto. Se o limite já existir, validar se é respeitado; se não existir, avaliar sua necessidade e o valor adequado.

## FEAT-004 — Presets de equipamentos

**Status:** sugestão.

Permitir salvar e nomear conjuntos de equipamentos e reaplicá-los sem trocar cada item manualmente, por exemplo: PvE, PvP, defesa e perfuração.

**Benefício:** facilitar o uso de builds específicas por situação. Ao aplicar um preset, informar se algum item não estiver disponível e respeitar as restrições de troca de equipamentos do jogo.

## FEAT-005 — Trancar itens na mochila

**Status:** sugestão.

Adicionar uma opção para trancar e destrancar itens, com indicação visual clara. Itens trancados devem ficar protegidos contra venda individual, venda em lote e descarte até serem destrancados.

**Benefício:** evitar perder equipamentos por engano, especialmente itens guardados para outras builds.

## FEAT-006 — Consumíveis como drops ocasionais de NPCs

**Status:** sugestão.

Permitir que alguns NPCs dropem ocasionalmente consumíveis de regeneração de HP, recuperação de escudo e aumento temporário de velocidade de movimento.

**Benefício:** diversificar recompensas e oferecer recursos úteis durante a exploração. Avaliar frequência, quantidade e efeito na economia para evitar estoque excessivo ou consumo obrigatório em todo combate.

## FEAT-007 — Baús pelo mapa abertos com chaves

**Status:** sugestão.

Distribuir baús pelo mapa que possam ser abertos ao ter uma chave no inventário ou comprar uma chave. Definir como as chaves são obtidas e se são consumidas na abertura.

**Benefício:** criar oportunidades de exploração e recompensas além do combate. Mostrar o requisito da chave e confirmar seu uso antes de consumi-la.

## FEAT-008 — Proteção da zona segura condicionada ao fim do combate

**Status:** sugestão de regra de combate e balanceamento; comportamento atual ainda não validado.

Entrar na zona segura perto do porto enquanto estiver em combate deve manter o jogador em combate, sem conceder proteção automaticamente. A proteção da zona só deve ser ativada quando o jogador estiver dentro dela e fora de combate há **X segundos**, com o tempo ainda a definir.

**Objetivo:** impedir que correr para o porto durante uma luta conceda segurança imediata e permita escapar usando a borda da zona.

**Pontos a definir:** quais eventos iniciam e renovam o estado de combate (incluindo dano contínuo e projéteis em trânsito), quando começa a contagem de X segundos e como ações ofensivas afetam a proteção. A regra deve impedir atacar a partir da zona mantendo proteção indevida.

**Indicação na interface:** distinguir estar dentro da zona de estar efetivamente protegido e mostrar quando o combate ou a espera impedem a proteção.

**Cenários para validar:** entrar durante uma luta; entrar já fora de combate há X segundos; encerrar o combate dentro da zona e aguardar o prazo; receber novo dano durante a espera; atravessar repetidamente a borda da zona. Confirmar que a proteção só é concedida quando as condições forem atendidas.

## FEAT-009 — Desafios de progressão a cada 20 níveis

**Status:** sugestão; periodicidade e regra de desbloqueio a avaliar.

Introduzir um teste ou desafio a cada 20 níveis para variar a progressão: derrotar determinados NPCs em um mapa, vencer o boss da região ou combinar objetivos diferentes.

**Objetivo:** dar marcos à evolução e reduzir a sequência repetitiva de matar monstros e subir de nível. Definir se o desafio desbloqueia a próxima faixa de níveis ou oferece uma recompensa opcional. Se for obrigatório, garantir acesso ao objetivo e dificuldade adequada para evitar bloquear a progressão injustamente.

Relacionado ao relato sobre EXP de missões repetitivas, registrado como BAL-001 em [Observações de Balanceamento](Observações%20de%20Balanceamento.md).

## FEAT-010 — Item para trocar um atributo do equipamento

**Status:** sugestão de recompensa ou item raro futuro.

Permitir escolher um atributo específico do equipamento para substituir, preservando os demais. Poderia haver versões do consumível: uma sorteia o novo atributo; outra, mais especial, permite escolher entre atributos elegíveis.

**Regra sugerida para a versão selecionável:** impedir escolher um atributo que já esteja presente em outro slot de atributo do mesmo equipamento. Confirmar o alcance dessa restrição antes de implementar.

**Benefício:** permitir ajustar itens para builds específicas. Definir atributos elegíveis, faixas de valores, custo e consumo do item; apresentar claramente o resultado ou as possibilidades antes de confirmar a troca.

![Comparação de atributos de equipamentos](evidencias/FEAT-010-atributos-equipamento.png)

## FEAT-011 — Aba de mascotes em Bolsa & Navio

**Status:** sugestão de organização da interface.

Mover o gerenciamento dos mascotes para uma aba de **Bolsa & Navio**, assim como já ocorreu com as skins, reduzindo a quantidade de menus no topo. Manter disponíveis as informações e ações atuais de seleção do mascote.

![Bolsa & Navio e janela atual de mascotes](evidencias/FEAT-011-mascotes.png)

## FEAT-012 — Cards de skins consistentes com os mascotes

**Status:** sugestão visual.

Exibir skins em cards menores, lado a lado, seguindo o padrão visual dos mascotes. Preservar a identificação da skin em uso, a prévia, a descrição e a ação de selecionar, adaptando a quantidade de colunas ao espaço disponível.

![Comparação entre a apresentação de skins e mascotes](evidencias/FEAT-012-skins-mascotes.png)

## FEAT-013 — Pequenos bônus de atributos em skins

**Status:** ideia futura para avaliação de balanceamento.

Avaliar skins com bônus de atributos, de forma semelhante aos mascotes. Exemplos propostos: +5% de dano, +5% de redução de dano ou outros efeitos distintos. Esses valores são sugestões, não números aprovados.

**Ponto a avaliar:** a interface atual informa que skins mudam somente a aparência. Adicionar bônus altera esse contrato e exige atualizar a comunicação. Medir o impacto combinado com equipamentos, mascotes e buffs, pois 5% pode ter efeito relevante no endgame. Definir também se apenas a skin equipada concede o bônus e como cada opção é obtida.

## FEAT-014 — Campo de busca na loja

**Status:** sugestão de usabilidade.

Adicionar um campo de busca por nome para encontrar itens na loja sem percorrer toda a lista. Permitir limpar a busca e indicar quando nenhum resultado for encontrado. Deixar claro se a busca filtra a aba atual ou toda a loja.

**Benefício:** agilizar a compra, principalmente conforme o catálogo crescer.

## FEAT-015 — Quantidade e preço claros nos botões de compra

**Status:** sugestão de clareza da interface.

Atualmente os botões mostram pares como **50 · 50** e **250 · 250**, sem rótulos que distingam a quantidade recebida do valor pago. A captura também mostra pares com valores diferentes, como **50 · 250**, mantendo a mesma ambiguidade.

Apresentar explicitamente a quantidade e o preço total do pacote, identificando a moeda por ícone ou nome. Exemplo de formato: **Comprar 50 un. — 250 [moeda]**. Se necessário, usar duas linhas: **Quantidade: 50** e **Preço: 250 [moeda]**.

**Benefício:** permitir entender o que será recebido e quanto será gasto antes da compra. Confirmar a ordem dos valores atuais e a moeda utilizada antes de aplicar os rótulos.

![Loja com botões de quantidade e preço sem identificação explícita](evidencias/FEAT-014-015-loja.png)

## FEAT-016 — Talento de magnetismo para coleta de baús

**Status:** sugestão.

Adicionar um talento de magnetismo que aumente a distância a partir da qual os baús dropados começam a ser atraídos até o jogador. O alcance cresce conforme a quantidade de pontos investidos.

**Benefício:** oferecer uma opção de conveniência na árvore de talentos, facilitando a coleta durante a navegação.

**Pontos a definir:** alcance base, aumento por ponto, quantidade máxima de pontos e posição na árvore. Mostrar o alcance atual e o ganho do próximo ponto na descrição do talento.

O talento aumenta o alcance de atração. A falha em que o baú não consegue alcançar um navio em movimento continua registrada como **BUG-002** em [Bugs Encontrados](Bugs%20Encontrados.md) e precisa ser corrigida independentemente do investimento nesse talento.

![Árvore de talentos como referência para a sugestão de magnetismo](evidencias/FEAT-016-talentos-magnetismo.png)

## FEAT-017 — Item de escudo para uso estratégico

**Status:** sugestão motivada pelo combate com Leviatã Primordial (BAL-006).

Adicionar um item que conceda proteção temporária e possa ser ativado em um momento específico para responder a ataques fortes anunciados, como a emergência do boss após submergir.

**Objetivo:** oferecer uma decisão de timing e uma chance de sobrevivência, mantendo o desafio do encontro.

**Pontos a definir:** duração, quantidade de dano absorvida ou reduzida, recarga, custo e interação com outras defesas. Garantir sinalização e tempo suficiente para uso. Avaliar o impacto em PvE e PvP e evitar que a sobrevivência dependa exclusivamente de um item pago ou de difícil acesso.

## FEAT-018 — Respawn em local aleatório do mapa

**Status:** sugestão para avaliação.

Após o naufrágio, permitir que o jogador reapareça em um local aleatório do mesmo mapa, como alternativa ao retorno fixo ao porto.

**Pontos a avaliar:** selecionar posições válidas e seguras, evitando obstáculos, bosses e inimigos próximos que provoquem uma nova morte imediata. Definir se substitui o respawn no porto ou se o jogador pode escolher entre as duas opções.

Avaliar o impacto no deslocamento, nas lutas em grupo e no PvP, para que morrer não se torne um atalho vantajoso nem permita retornar imediatamente à luta sem consequência.

## Referências visuais

Capturas da interface de equipamentos, inventário e atributos usadas como contexto para as sugestões. Elas não comprovam a ausência dos recursos propostos.

![Inventário e atributos do navio](evidencias/FEAT-inventario-atributos.png)

![Tela Bolsa & Navio](evidencias/FEAT-bolsa-e-navio.png)
