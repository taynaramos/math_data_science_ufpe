# Atividade

Atividade para a matéria de Matemática para Ciência de Dados da especialização em Deep Learning do CIn-UFPE.

## Descrição

Pegar o exemplo dado na aula que usava sigmóide como função de ativação, fazer alguma alteração e observar os resultados.

## Modificaçoes feitas

Para a atividade, escolhi utilizar a função de ativação ReLU, já que é uma função de ativação geral e é usada amplamente hoje. Além disso, deixei o sigmóide na camada de saída, pois a ReLU deve ser usada apenas nas camadas ocultas.
Com essa mudança, o erro estabilizou mais rápido (na implementação manual), portanto decidi também aumentar e colocar 4 neurônios na rede.

## Resultados

Inicialmente, foi realizado um teste utilizando apenas 2 neurônios na camada oculta com a função de ativação ReLU. Durante a execução, observou-se que o erro (loss) estagnou rapidamente nas primeiras épocas do treinamento. Para investigar se o problema era a limitação de capacidade da rede, aumentou-se a arquitetura para 4 neurônios. No entanto, o comportamento permaneceu semelhante: apesar da convergência inicial acelerada, a perda voltou a estabilizar sem reduções expressivas, mantendo a acurácia em um patamar muito próximo (~87% no treino manual e ~89% no Keras). Esse resultado indica que a estagnação não ocorreu por falta de neurônios, mas talvez por não ter mudado taxa de aprendizado, que se mostrou menos suave para este problema do que a ativação Sigmóide original.

| Métrica | Experimento 1 (Sigmóide - 2 Neurônios) | Experimento 2 (ReLU - 4 Neurônios) |
| :--- | :--- | :--- |
| **Acurácia Inicial** | 50% | 50% |
| **Loss Inicial (Manual)** | 18.39 | 19.58 |
| **Loss Final (Manual)** | 3.50 | 4.35 |
| **Acurácia Final (Manual)** | 91% (`acc 91`) | 87% (`acc 87`) |
| **Acurácia Keras** | 91% (`accuracy: 0.9100`) | 89% (`accuracy: 0.8900`) |
| **Loss Keras** | 0.0710 | 0.0797 |

Para acessar no google colab acesse o [link](https://colab.research.google.com/drive/1PEpZmuJtYT_lPrADBDv3IpZWPM2CvDM7?usp=sharing) 