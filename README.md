# Algoritmo Genético para o Problema da Mochila

Este projeto implementa um **Algoritmo Genético** para resolver o **Problema da Mochila**. O objetivo é selecionar os itens que devem ser colocados em uma mochila de modo a maximizar o valor total dos itens sem exceder um peso máximo permitido. Além disso, o algoritmo retorna os cinco melhores indivíduos (soluções) de cada geração e ao final de todas as gerações.

## Descrição

O **Problema da Mochila** é um problema clássico de otimização combinatória. Dada uma lista de itens, onde cada item tem um peso e um valor associado, o algoritmo deve selecionar um subconjunto desses itens que maximize o valor total sem que o peso total exceda um limite especificado.

Neste projeto, usamos um **algoritmo genético** para encontrar uma solução aproximada para o problema. O algoritmo genético simula o processo de evolução natural, utilizando operações como **crossover**, **mutação**, e **seleção por torneio** para evoluir uma população de soluções ao longo de várias gerações.

## Funcionamento

1. **População Inicial**: O algoritmo começa com uma população de cromossomos (soluções) gerados aleatoriamente. Cada cromossomo é representado por um vetor binário, onde cada bit indica se um item foi ou não incluído na mochila.
2. **Avaliação**: Cada cromossomo é avaliado com base no valor total dos itens selecionados e na penalização para soluções que excedem o peso máximo.
3. **Crossover e Mutação**: Novas soluções são geradas através da combinação de dois "pais" (crossover) e, com uma pequena probabilidade, a solução pode sofrer mutação, alterando alguns de seus genes.
4. **Seleção**: O algoritmo seleciona os melhores indivíduos para passar para a próxima geração, utilizando o método de **torneio**.
5. **Resultados**: A cada geração, os cinco melhores indivíduos são registrados. Ao final de todas as gerações, o algoritmo retorna os cinco melhores indivíduos finais.

## Exemplo de Uso

```python
pesos_e_valores = [[2, 10], [4, 30], [6, 300], [8, 10], [8, 30], [8, 300], [12, 50], [25, 75], [50, 100], [100, 400]]
peso_maximo = 100
num_cromossomos = 150
geracoes = 50

resultado = algoritmo_genetico_mochila(pesos_e_valores, peso_maximo, num_cromossomos, geracoes)
print(f'Resultado final: {resultado}')



# Algoritmo Genético para Minimização de f(x) = x³ - 6x + 14

Este projeto implementa um **Algoritmo Genético (AG)** para encontrar o valor de `x` que minimiza a função matemática `f(x) = x³ - 6x + 14`. O AG simula o processo de evolução natural, utilizando operações genéticas como **crossover**, **mutação**, e **seleção** para otimizar uma população de soluções ao longo de várias gerações.

## Descrição do Algoritmo

O algoritmo genético é uma técnica de busca estocástica baseada nos princípios de evolução natural, como seleção, reprodução, mutação e sobrevivência dos mais aptos. O objetivo deste algoritmo é encontrar o valor de `x` que minimiza a função objetivo `f(x) = x³ - 6x + 14`.

### Características

- **Representação Binária**: O valor de `x` é representado como um vetor binário. O número de bits necessário para representar `x` depende da faixa de valores entre `x_min` e `x_max` e da precisão desejada.
- **Seleção por Torneio**: Utiliza o método de seleção por torneio para escolher os indivíduos mais aptos.
- **Crossover**: Aplica crossover entre dois indivíduos (pai e mãe) para gerar novos indivíduos. Suporta crossover com um ou dois pontos de corte.
- **Mutação**: Aplica mutação em cada gene do indivíduo com uma determinada taxa de mutação.
- **Elitismo**: Implementa elitismo, garantindo que uma porcentagem dos melhores indivíduos da geração anterior seja mantida na próxima geração.

## Funcionamento

1. **População Inicial**: Uma população inicial de soluções (indivíduos) é gerada aleatoriamente.
2. **Avaliação**: Cada indivíduo é avaliado com base na função objetivo `f(x) = x³ - 6x + 14`.
3. **Seleção**: O algoritmo seleciona os indivíduos mais aptos da população para reprodução, utilizando o método de torneio.
4. **Crossover e Mutação**: Novos indivíduos são gerados através de crossover e mutação.
5. **Elitismo**: Uma porcentagem dos melhores indivíduos de cada geração é mantida na próxima geração.
6. **Iteração**: O processo se repete por um número definido de gerações, retornando o melhor valor de `x` que minimiza a função objetivo.

## Parâmetros Configuráveis

- `x_min`: Valor mínimo de `x` no intervalo de busca.
- `x_max`: Valor máximo de `x` no intervalo de busca.
- `tam_populacao`: Tamanho da população.
- `taxa_mutacao`: Probabilidade de mutação em cada gene.
- `taxa_crossover`: Probabilidade de crossover entre dois indivíduos.
- `num_geracoes`: Número de gerações a serem evoluídas.
- `elitismo`: Habilita ou desabilita o elitismo.
- `percent_elitismo`: Percentual de indivíduos de elite mantidos na nova geração.
- `pontos_corte`: Número de pontos de corte no crossover (1 ou 2).

## Exemplo de Uso

```python
if __name__ == "__main__":
    ag = AlgoritmoGenetico(x_min=-10, x_max=10, tam_populacao=10, taxa_mutacao=0.01, taxa_crossover=0.7, num_geracoes=100, elitismo=True, percent_elitismo=0.1, pontos_corte=2)
    melhor_x, melhor_fitness = ag.executar()
    print(f'\nMelhor solução: x = {melhor_x}, f(x) = {melhor_fitness}')



