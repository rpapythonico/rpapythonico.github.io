# Aula 2 - Listas, Dicionários e Loopings

## Lista:

- list() ou [ ]
    - Ex.:
        
        ```python
        lista = ['Thomas', 'Wilber', 'Marcos', 'Pedro']
        ```
        
- .pop
    - Ex.:
        
        ```python
        lista.pop()
        print(lista)
        # output: ['Thomas', 'Wilber', 'Marcos']
        ```
        
- .append()
    - Ex.:
        
        ```python
        lista.append('Fernando')
        print(lista)
        # output: ['Thomas', 'Wilber', 'Marcos', 'Fernando']
        ```
        
- .remove()
    - Ex.:
        
        ```python
        lista.remove('Marcos')
        print(lista)
        # output: ['Thomas', 'Wilber', 'Fernando']
        ```
        
- Slice:
    - Ex.:
        
        ```python
        print(lista[1:3])
        # output: ['Thomas', 'Wilber']
        ```
        

## Dicionário:

- dict() ou { }
    - Ex.:
        
        ```python
        fruta = {}
        fruta['maca'] = 'É uma fruta vermelha'
        fruta['limao'] = 'É uma fruta verde'
        fruta['banana'] = 'É uma fruta amarela'
        
        #ou
        
        fruta = {'maca': 'É uma fruta vermelha', 'limao': 'É uma fruta verde', 'banana': 'É uma fruta amarela'}
        ```
        
- .keys()
    - Ex.:
        
        ```python
        fruta.keys()
        # output: dict_keys(['maca', 'limao', 'banana'])
        ```
        
- .values()
    - Ex.:
        
        ```python
        fruta.values()
        # output: dict_values(['É uma fruta vermelha', 'É uma fruta verde', 'É uma fruta amarela'])
        ```
        
- items()
    - Ex.:
        
        ```python
        fruta.items()
        # output: dict_items([('maca', 'É uma fruta vermelha'), ('limao', 'É uma fruta verde'), ('banana', 'É uma fruta amarela')])
        ```
        

## Loopings:

### For:

- Looping com uma quantidade definida:
    
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
    
- Looping usando um intervalo de números:
    
    ```python
    for numero in range(3, 8):
    	print(numero)
    
    # output:
    # 3
    # 4
    # 5
    # 6
    # 7
    ```
    
- Looping usando listas como delimitador:
    
    ```python
    lista_de_filmes = ['Kill Bill', 'Pulp Fiction', 'Cães de Aluguel']
    for filme in lista_de_filmes:
        print(filme)
    
    # output:
    # Kill Bill
    # Pulp Fiction
    # Cães de Aluguel
    ```
    
- Looping usando listas com seus respectivos índices:
    
    ```python
    lista_de_filmes = ['Kill Bill', 'Pulp Fiction', 'Cães de Aluguel']
    for indice, filme in enumerate(lista_de_filmes):
    print(indice, '-', filme)
    
    # output:
    # 0 - Kill Bill
    # 1 - Pulp Fiction
    # 2 - Cães de Aluguel
    ```
    

### While:

- Looping condicional utilizando incrementador:
    
    ```python
    contador = 0
    while contador < 5:
    	print(f'O contador é {contador} e ainda é menor que 5!')
    	contador+= 1
    
    # output:
    # O contador é 0 e ainda é menor que 5!
    # O contador é 1 e ainda é menor que 5!
    # O contador é 2 e ainda é menor que 5!
    # O contador é 3 e ainda é menor que 5!
    # O contador é 4 e ainda é menor que 5!
    ```
    
- Looping condicional infinito com "input":
    
    ```python
    nome = ''
    while nome != 'seu nome':
    	nome = input('Insira seu nome: ')
    print('Parabéns, você entendeu a brincadeira!')
    ```
    
- Looping condicional infinito com "break" e "continue":
    
    ```python
    valor = 0
    while True:
    	num = input('Insira um valor para a soma: ')
    	if num != 'q':
    		valor+=int(num)
    		print(f'\nAgora o valor é: {valor}\n')
    		continue
    	else:
    		break
    print('Looping encerrado!')
    
    # output:
    # Insira um valor para a soma: 2
    # Agora o valor é: 2
    # Insira um valor para a soma: 4
    # Agora o valor é: 6
    # Insira um valor para a soma: q
    # Looping encerrado!
    ```