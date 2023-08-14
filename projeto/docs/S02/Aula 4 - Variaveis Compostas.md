# O que é uma variável composta (e para que serve)?

## Explicação - Simplificada

Assim como é possível armazenar **um** valor dentro da variável, o Python também permite armazenar vários valores dentro de uma única variável.

Ex.: Uma lista de compras pode conter um ou mais produtos, ou seja, a variável consegue comportar N valores para serem acessados posteriormente.

## Quais os tipos de variáveis compostas?

- **tuple**: Armazena N valores e são **imutáveis**. É representada por **parênteses**.
    - Ex.: 

            frutas = ('Limão', 'Maça', 'Melancia', 'Banana')

- **list**: Armazena N valores e são **mutáveis**. É representada por **colchetes**.
    - Ex.: 

            nomes = ['Thomas', 'Matheus', 'Felipe', 'Fernanda']

- **set**: Armazena N valores, são **imutáveis** e **não** permite **duplicatas**. É representada por **chaves**.
    - Ex.: 

            numeros = {1, 2, 3, 4, 5}

- **dict**: Armazena N valores, tendo como princípio uma **chave e um valor**, podendo também ter **uma chave para vários valores** (lista). É **mutável**. E é representada por **chaves e dois pontos**.
    - Ex.: 

            objetos = {'Morango': 'É uma fruta', 'Caneca': 'É um objeto', 'Carro': 'É um automovel'}

## Listas

- Cria uma lista

        alunos = ['Marcos', 'Henrique', 'Julia', 'Guilherme']

- Retira um valor da lista pelo **índice**

        alunos.pop(-1)
        print(alunos)
        # output: ['Marcos', 'Henrique', 'Julia']

- Retira um valor da lista pelo **nome**

        alunos.remove('Marcos')
        print(alunos)
        # output: ['Henrique', 'Julia']

- Acrescenta um novo valor na lista

        alunos.append('Renan')
        print(alunos)
        # output: ['Henrique', 'Julia', 'Renan']

- Consulta valores na lista pelo índice

        alunos[1]
        # output: 'Julia'
        alunos[1:3]
        # output: ['Julia', 'Renan']
        alunos[0]
        # output: 'Henrique'
        alunos[-1]
        # output: 'Renan'

- Valida o tamanho da lista

        len(alunos)
        # output: 3
            
## Dicionario

- Cria um dicionário

        contatos = {'Marcos': '1234-5678', 'Henrique': '9999-9999', 'Julia': '8765-4321', 'Guilherme': '8877-7788'}

- Emite todas as chaves do dicionário

        contatos.keys()
        # output: dict_keys(['Marcos', 'Henrique', 'Julia', 'Guilherme'])

- Emite todos os valores de cada chave do dicionário

        contatos.values()
        # output: dict_values(['1234-5678', '9999-9999', '8765-4321', '8877-7788'])

- Emite todos os valores registrados no dicionario - (chave(s) e valor(es))

        contatos.items()
        # output: dict_items([('Marcos', '1234-5678'), ('Henrique', '9999-9999'), ('Julia', '8765-4321'), ('Guilherme', '8877-7788')])

- Deleta valores através da chave:

        del(contatos['Marcos'])
        # output: {'Henrique': '9999-9999', 'Julia': '8765-4321', 'Guilherme': '8877-7788'}

- Acessa valores de uma chave:

        contatos.get('Julia')
        # output: '8765-4321'

        # ou

        contatos['Julia']
        # output: '8765-4321'

- Adiciona uma nova chave com seu respectivo valor

        contatos['Ana'] = '0000-9999'
        print(contatos)
        # output: {'Marcos': '1234-5678', 'Henrique': '9999-9999', 'Julia': '8765-4321', 'Guilherme': '8877-7788', 'Ana': '0000-9999'}

- Cria um dicionário através de uma lista de tuplas

        contatos_listas = [
            ('Marcos', '1234-5678'),
            ('Henrique', '9999-9999'),
            ('Julia', '8765-4321'),
            ('Guilherme', '8877-7788')
        ]
        contatos = dict(contatos_listas)
        print(contatos)
        # output: {'Marcos': '1234-5678', 'Henrique': '9999-9999', 'Julia': '8765-4321', 'Guilherme': '8877-7788'}