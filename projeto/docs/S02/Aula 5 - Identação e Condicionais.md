# Identação e Condicionais

## Identação

Em muitas linguagens de programação, ao utilizarmos alguma função que exija mais de uma linha, é posto um símbolo que delimite seu começo e fim. No Python, usamos os dois pontos e uma identação (tecla TAB) para dizer o que está dentro da funcionalidade que estamos chamando. Vamos ver isso na prática com as condições.

## Condicionais

Assim como nem tudo só é verdadeiro ou falso, na linguagem de programação também pode-se ter tomadas de decisão para que o código realize determinadas ações quando tiver algum comportamento especificado.

O condicional é composto de:

- **if** (a primeira condição do código)
- **elif** (uma ou mais condições durante as validações)
- **else** (condição final a qual será ativada se nenhuma das verificações acima forem verdadeira)

A sintaxe mínima de uma condicional possui um **if** e um **else**:
```python
if idade >= 18:
  print('Maioridade')
else:
  print('Menoridade')
```

Já quando é necessário ter caminhos alternativos, deve ser utilizado o **elif**:

```python
if idade >= 16 and idade < 18:
    print('Você está perto da maioridade, seu voto é OPCIONAL!')
elif idade >= 18 and idade < 70:
    print('Você é de maior e seu voto é OBRIGATÓRIO!')
elif idade >= 70:
    print('Você já nos ajudou bastante até agora, seu voto agora é OPCIONAL!')
else:
    print('Infelizmente você AINDA NÃO está com a idade mínima para votar.')
```