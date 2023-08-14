# Manipulação de Strings

## Strings Vazias

Tem como objetivo esvaziar uma variável criada anteriormente ou servir como validação para caso não seja localizado nenhuma correspondência durante uma coleta de dados em **strings**.

```python
variavel_vazia = ""
# ou
variavel_vazia = None
```

## Cortando uma String

1. Gerar uma variável com o texto:
    ```python
    paragrafo = "Lorem Ipsum is simply dummy text of the printing and typesetting industry."
    ```
2. Cortar o texto selecionando do começo ao caractere "X":
    ```python
    paragrafo[:50]
    # output: 'Lorem Ipsum is simply dummy text of the printing a'
    ```

3. Cortar o texto selecionando do caractere "X" até o final:
    ```python
    paragrafo[30:]
    # output: 'xt of the printing and typesetting industry.'
    ```
4. Cortar o texto selecionando do caractere "X" até o "Y":
    ```python
    paragrafo[30:50]
    # output: 'xt of the printing a'
    ```

## Localizar uma letra ou palavra:

1. Gerar uma variável com o texto:
    ```python
    paragrafo = "Lorem Ipsum is simply dummy text of the printing and typesetting industry."
    ```
2. Buscar a letra ou palavra desejada:
    ```python
    paragrafo.find('t')
    # output: 28
    paragrafo.find('printing')
    # output: 40
    ```

## Checar se uma palavra existe ou não existe:

1. Gerar uma variável com o texto:
    ```python
    paragrafo = "Lorem Ipsum is simply dummy text of the printing and typesetting industry."
    ```
2. Buscar a letra ou palavra desejada:
    ```python
    "Lorem Ipsum" in paragrafo
    # output: True
    "Python" not in paragrafo
    # output: True
    ```

## Deixar um texto com letras maiúsculas ou minúsculas

1. Gerar uma variável com o texto:
    ```python
    paragrafo = "Lorem Ipsum is simply dummy text of the printing and typesetting industry."
    ```

2. Deixando letras **maiúsculas**:
    ```python
    paragrafo.upper()
    # output: 'LOREM IPSUM IS SIMPLY DUMMY TEXT OF THE PRINTING AND TYPESETTING INDUSTRY.'
    ```

3. Deixando letras **minúsculas**:
    ```python
    paragrafo.lower()
    # output: 'lorem ipsum is simply dummy text of the printing and typesetting industry.'
    ```

## Deixando o texto em formato de parágrafo ou título
1. Gerar uma variável com o texto:
    ```python
    paragrafo = "Lorem Ipsum is simply dummy text of the printing and typesetting industry."
    ```

2. Deixando em formato de título:
    ```python
    paragrafo.title()
    # output: 'Lorem Ipsum Is Simply Dummy Text Of The Printing And Typesetting Industry.'
    ```
3. Deixando em formato de parágrafo:
    ```python
    paragrafo.capitalize()
    # output: 'Lorem ipsum is simply dummy text of the printing and typesetting industry.'
    ```

## Checagem de palavra no começo ou no final

1. Gerar uma variável com o texto:
    ```python
    paragrafo = "Lorem Ipsum is simply dummy text of the printing and typesetting industry."
    ```

2. Validar uma palavra no começo:
    ```python
    paragrafo.startswith("Lorem")
    # output: True

    paragrafo.startswith("Python")
    # output: False
    ```

3. Validar uma palavra no começo:
    ```python
    paragrafo.endswith(".")
    # output: True

    paragrafo.endswith("ipsum")
    # output: False
    ```

## Texto para lista e vice e versa

- Separar uma string em list através de um delimitador:
    ```python
    paragrafo = "Lorem Ipsum is simply dummy text of the printing and typesetting industry."

    paragrafo.split(" ")
    # output: ['Lorem', 'Ipsum', 'is', 'simply', 'dummy', 'text', 'of', 'the', 'printing', 'and', 'typesetting', 'industry.']
    ```
    
- Juntar uma list em string através de um delimitador:
    ```python
    paragrafo = ['Lorem', 'Ipsum', 'is', 'simply', 'dummy', 'text', 'of', 'the', 'printing', 'and', 'typesetting', 'industry.']

    ";".join(paragrafo)
    # output: 'Lorem;Ipsum;is;simply;dummy;text;of;the;printing;and;typesetting;industry.'
    ```

## Preenchimento com zeros

1. Gerar uma variável com o texto:
    ```python
    cpf_sem_mascara = "123456789"
    ```

2. Completar com zeros até chegar no limite de caracteres
    - Esse limite é inserido durante a chamada da função.
    ```python
    cpf_sem_mascara.zfill(11)
    # output: '00123456789'
    ```

## Limpas espaços indevidos no começo e no final de uma palavra/texto:

1. Gerar uma variável com o texto:
    ```python
    texto = "         O Real é a moeda corrente oficial da República Federativa do Brasil.         "
    ```

2. Limpar espaços extras no começo e no final:
    ```python
    texto.strip()
    # output: 'O Real (ISO 4217: BRL, abreviado como R$[4]) é a moeda corrente oficial da República Federativa do Brasil.'
    ```

## Trocar ou eliminar alguma palavra ou frase:

1. Gerar uma variável com o texto:
    ```python
    texto = "O Real é a moeda corrente oficial da República Federativa do Brasil."
    ```

2. Substituir o(s) valor(es) desejado(s):
    ```python
    texto.replace('Real', 'DÓLAR NÃO')
    # output: 'O DÓLAR NÃO é a moeda corrente oficial da República Federativa do Brasil.'
    ```