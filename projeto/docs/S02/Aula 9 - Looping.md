# Looping

## Explicação

Muitas vezes durante um desenvolvimento, faz-se necessário percorrer uma lista ou até mesmo realizar contagens e para isso, o Python possui os **loopings**. Existem duas formas de fazer isso, o **For** e o **While**.

## Looping For

Permite percorrer os itens de uma coleção e para cada um deles executar o bloco de códigos declarado dentro da estrutura do looping.

### Exemplos

- Looping com uma quantidade definida de iterações
  ```python
  for numero in range(5):
    print(numero)
  # output: 
  # 0
  # 1
  # 2
  # 3
  # 4
  ```
  
- Looping usando intervalo de números
  ```python
  for numero in range(3, 10):
    print(numero)
    # output:
    # 3
    # 4
    # 5
    # 6
    # 7
    # 8
    # 9
  ```
  

- Looping usando listas/tuplas como delimitador
  ```python
  lista_de_filmes = ['Kill Bill', 'Madagascar', 'Harry Potter']

  # ou

  lista_de_filmes = ('Kill Bill', 'Madagascar', 'Harry Potter')

  for filme in lista_de_filmes:
    print(filme)
  # output:
  # 'Kill Bill'
  # 'Madagascar'
  # 'Harry Potter'
  ```

- Looping usando listas com seus respectivos índices
  ```python
  lista_de_filmes = ['Kill Bill', 'Madagascar', 'Harry Potter']

  for indice, filme in enumerate(lista_de_filmes):
    print(indice, '-', filme)
  # output: 
  # 0 - Kill Bill
  # 1 - Madagascar
  # 2 - Harry Potter
  ```

## Looping While

O comando while faz com que um conjunto de instruções seja executado enquanto uma condição é atendida.


### Exemplos

- **Looping condicional utilizando incrementador**

  - Cria-se uma condição para o looping em cima de uma variavel incrementavel. Toda vez que rodar o bloco de codigos, essa variável irá ter um valor somado. O looping rodará até que a condição passe a ser falsa.
  - Ex.:
    ```python
    contador = 0
    while contador < 5:
      print(f'O valor do contador é {contador} e ainda é menor que 5!')
      contador += 1
    # output:
    # O valor do contador é 0 e ainda é menor que 5!
    # O valor do contador é 1 e ainda é menor que 5!
    # O valor do contador é 2 e ainda é menor que 5!
    # O valor do contador é 3 e ainda é menor que 5!
    # O valor do contador é 4 e ainda é menor que 5!
    ```
- **Looping condicional infinito com 'input'**

  - O comando input permite que o usuario escreva valores para dentro do codigo durante a execução, com isso, no momento em que o usuario colocar a informação desejada, o looping encerrará a rotina.
  - Ex.:
    ```python
    comando = ''
    while comando != 'cancelar':
      print('Programa rodando....')
      comando = input('Você desejar cancelar? Se sim digite "cancelar": ').lower()
    print('Seu programa foi cancelado com sucesso!')
    ```


- **Looping condicional infinito com "break" e "continue"**

  - Este formato permite que a rotina rode eternamente. Isto ocorre, pois não é especificado nenhuma condição **"False"**, com isso, é necessário deixar implicito no codigo quando deve continuar rodando e quando deve parar a execução. Para isso, existem as palavras reservadas **"break"** e **"continue"**.
  - Ex."
    ```python
    valor = 0
    while True:
      num = input('Insira um valor para a soma: ')
      if num != 'q':
        valor += int(num)
        print(f'\nAgora o valor é: {valor}\n')
        continue
      else:
        print(f'Voce digitou "q" isso irá encerrar o programa.')
        break
    print('Looping encerrado!')
    ```