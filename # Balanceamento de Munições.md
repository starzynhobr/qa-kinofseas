# Balanceamento de Munições

## Problema atual

A munição explosiva possui dano adicional em área ao atingir o alvo, mas mesmo contra **um único inimigo** continua sendo uma das melhores opções de dano.

Isso cria um problema de balanceamento: o efeito em área deveria ser a principal vantagem da munição, mas ela não está pagando um custo significativo por essa vantagem.

Na prática, ela acaba sendo:

* Muito boa contra grupos.
* Muito boa contra alvo único.
* Pouco dependente da situação.
* Superior a munições especializadas.

Quando uma munição é ótima em praticamente todos os cenários, outras opções acabam existindo apenas visualmente, sem representar uma escolha real de gameplay.

\---

## Estrutura sugerida

Pode ser útil definir um **dano base de referência** para as munições e fazer cada uma trocar parte desse dano por alguma especialização.

Exemplo conceitual:

|Munição|Hit direto|Especialização|
|-|-:|-|
|Normal|100%|Nenhuma|
|Marauder|120%|Alto dano direto|
|Explosiva|80–90%|Dano em área|
|Fósforo|70–80%|Queimadura forte|
|Fogo Frio|80–90%|Queimadura + chance de congelar|
|Quebra-Coração|100–110%|Chance de stun|
|Sangrenta|80–90%|Grande bônus contra jogadores|

Os números são apenas exemplos. A ideia é cada munição possuir um **orçamento de poder**.

Quanto melhor o efeito especial, maior deve ser o custo em algum outro atributo.

\---

## Caso da munição explosiva

A munição explosiva deveria ganhar valor principalmente quando existem múltiplos inimigos próximos.

Por exemplo:

```text
Hit direto: 85%

Explosão:
+25% do dano para inimigos próximos

