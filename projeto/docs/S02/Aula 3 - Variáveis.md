# Variáveis

## O que é uma variável (e para que serve)?

### Explicação

#### Simplificada

É uma palavra (simples ou composta) utilizada para armazenar algum valor que poderá ser utilizado posteriormente pelo código.

Se assemelha ao conceito de carteira, onde são armazenados cartões/cédulas de dinheiro para ser usufruido quando necessário.

#### Técnica

Na programação, uma variável é um objeto (uma posição, frequentemente localizada na memória) capaz de reter e representar um valor ou expressão. Enquanto as variáveis só "existem" em tempo de execução, elas são associadas a "nomes", chamados identificadores, durante o tempo de desenvolvimento.

Via: [Wikipedia](https://pt.wikipedia.org/wiki/Vari%C3%A1vel_(programa%C3%A7%C3%A3o))

## Qual a forma certa de escrita de uma variável?

### Explicação

No Python é utilizado o formato **snake_case** para os casos onde possui uma nomenclatura composta (com mais de um palavra) e sempre será com **letras minúsculas**. Esse formato é chamado de **"Pythonico"**.

**Obs.:** Vale frisar que em âmbito corporativo, é sempre indicado usar termos em inglês para que o código fique de forma globalizada.

### Exemplo

```python
nome = "João"
# ou
idade = 18
# ou
nome_do_arquivo = "boleto.pdf"
# ou
numero_do_contrato = 123456789
```


# Quais os tipos de variáveis?

- **int**(eger): São valores inteiros.
    - Ex.: 1, 1, 2, 3, 5, 8, ...
- **str**(ing): São palavras/textos.
    - Ex.: Lorem Ipsum
- **float**: São valores "quebrados", isto é, com casas decimais.
    - Ex.: 3.14159265359
- **bool**(ean): São validações para perguntas fechadas, podendo ser "Verdadeiro" ou "Falso".
    - Ex.: True, False.

## Como converter?

- String para Integer:
    - Vale destacar que isso só é permitido através de números no formato string para integer.
    - Ex.:

            idade = int("12")

- Integer para String:
    - Ex.:

            cm = str(25)


- Integer para Boolean
    - Vale destacar que essa conversão só irá funcionar efetivamente com os números **0** e **1**.
        - 0: Não
        - 1: Sim
    - **Obs.:** Caso deseje usar números maiores que 1, o resultado sempre será **"True"**.
    - Ex.:

            variavel = bool(1)
            # ou
            variavel = bool(0)

- Integer para Float
    - Ex.:
    ```python
    volume = float(25)
    ```
- Float para Integer
    - Ex.:
    ```python
    pi = int(3.14)
    ```

- Float para String
    - Ex.:
    ```python
    peso = str(78.6)
    ```

- String para Float
    - Ex.:
    ```python
    altura = "1.82"
    altura = float(altura)
    # ou
    altura = "1,82"
    altura = altura.replace(',', '.')
    altura = float(altura)
    ```

- String para Boolean
    - Essa conversão sempre irá validar se existe algum valor à ser convertido, logo, sempre será "True" se não estiver vazio.
    - Ex.:
        ```python
        teste = bool("valor")
        # ou
        teste = bool()
        ```