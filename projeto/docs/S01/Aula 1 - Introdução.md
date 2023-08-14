# Aula 1 - Introdução

## Instalação:

- [https://www.python.org/downloads/](https://www.python.org/downloads/)
    - Download Python 3.10.2
- [https://www.anaconda.com/products/individual#Downloads](https://www.anaconda.com/products/individual#Downloads)
    - 64-Bit Graphical Installer (510 MB)

## IDEs:

- Google Collab:
    - [https://colab.research.google.com/](https://colab.research.google.com/)
- Jupyter Notebook:
    - [https://jupyter.org/install](https://jupyter.org/install)
- PyCharm:
    - [https://www.jetbrains.com/pt-br/pycharm/download/](https://www.jetbrains.com/pt-br/pycharm/download/)
- Visual Code:
    - [https://code.visualstudio.com/Download](https://code.visualstudio.com/Download)

## Guia:

### Variáveis;

- Armazenar valores para serem usados depois.
- O conceito na vida real se assemelha como um bolso de calça onde você pode guardar suas chaves.

### print();

- Emite dados na tela quando se quer apresentar algo ao usuário ou para testes;
- Ex.:
    
    ```python
    texto = 'Hello World'
    print(texto)
    ```
    

### Tipagem;

- int()
    - Valores numéricos inteiros (isto é, **SEM** casas decimais).
- float()
    - Valores numéricos reais (isto é, **COM** casas decimais).
- string()
    - Letras/texto.
- bool()
    - Validador.
    - Verdadeiro ou Falso
    - Sintaxe: True/False
- Ex.:
    
    ```python
    valor = 1
    
    valor = int(valor)
    #output: 1
    
    valor = float(valor)
    #output: 1.0
    
    valor = string(valor)
    #output: '1'
    
    valor = bool(valor)
    #output: True
    ```
    

### Tupla;

- ( )
- São imutáveis;
- Ex.:
    
    ```python
    #atribuição composta
    tupla_de_bandas = 'Led Zeppelin', 'The Doors', 'Black Sabbath'
    
    #ou
    
    tupla_de_bandas = ('Led Zeppelin', 'The Doors', 'Black Sabbath')
    ```
    

### Lista:

- [ ]
- São mutáveis;
- Ex.:
    
    ```python
    lista_de_livros = ['Harry Potter', 'Sherlock Holmes', 'Jogos Vorazes']
    ```
    

### Identação;

- Tab;
- Tabs definem o alinhamento dentro de alguma condição, looping ou função dentro do Python.

### Condição;

- if, elif e else
- Ex.:
    
    ```python
    idade = 17
    if idade idade < 16:
    	print('Adolescente')
    elif idade > 16 and < 21:
    	print('Jovem')
    else:
    	print('Adulto')
    ```
    

### len();

- Ex.:
    
    ```python
    texto = 'Lorem Ipsum is simply dummy text of the printing and typesetting industry.'
    len(texto)
    #output: 74
    ```
    

### input();

- Ex.:
    
    ```python
    nome = input('Qual o seu nome? R: ')
    print(nome)
    ```
    

### Comentários.

- # e "" ""
- Servem para criar "comentários" no código e assim facilitar a leitura dele por você mesmo ou outra pessoa.
- Ex.:
    
    ```python
    #Essa variavel receberá um valor e já terá seu dado convertido para inteiro
    valor_dois = int(input('Insira um novo valor para a soma: '))
    
    #ou
    
    print('Inicial')
    """Este
    é
    um
    comentário """
    ''' '''
    print('Final')
    ```
    

## Colinha:

- '=' passa valores
- '==' compara se os valores são iguais
- 'in' para checar algum valor
- '=== ' compara o valor e o tipo da variável

## Referências:

- Automatize tarefas maçantes com Python
    - [https://www.amazon.com.br/Automatize-tarefas-maçantes-com-Python-ebook/dp/B075JTQYB7](https://www.amazon.com.br/Automatize-tarefas-ma%C3%A7antes-com-Python-ebook/dp/B075JTQYB7)
- Curso Intensivo de Python
    - [https://www.amazon.com.br/Curso-Intensivo-Python-Introdução-Programação/dp/8575225030/](https://www.amazon.com.br/Curso-Intensivo-Python-Introdu%C3%A7%C3%A3o-Programa%C3%A7%C3%A3o/dp/8575225030/)