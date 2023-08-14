# RegEx

## Explicação

RegEx correspondem a descrições para um padrão de texto. Ou seja, são caracteres especiais que indicam determinados tipos de letras/números.

## Exemplo

### Importando a biblioteca

```python
import re
```

### Separando padrões em grupos

Para que os padrões sejam "encapsulados" em grupos menores, o símbolo utilizado são os parenteses. Através deles, será possível acessar a combinação desejada por um index, conforme exemplo abaixo:

```python
valida_tel = re.compile(r"(\d{2})\s(\d{4,5})\-(\d{4})")
coleta = valida_tel.search("Meu número é 41 99123-4567")

coleta.group()
# output: '41 99123-4567'

coleta.group(1)
# output: '41'

coleta.group(2)
# output: '99123'

coleta.group(3)
# output: '4567'
```

### Buscando por uma palavra inteira ou parcialmente

O símbolo de pipe "|" é utilizado em algumas linguagens de programação para apresentar a expressão "ou".


#### Exemplo 1

```python
regex_ou = re.compile(r"Wilber|Thomas")
coleta = regex_ou.search("Ola, meu nome e Wilber")
coleta.group()
# output: 'Wilber'

coleta = regex_ou.search("Ola, meu nome e Thomas")
coleta.group()
# output: 'Thomas'
```

#### Exemplo 2

```python
regex_ou = re.compile("Wil(ber|mar)")
coleta = regex_ou.search("Ola, meu nome e Wilber")
coleta.group()
# output: 'Wilber'

coleta = regex_ou.search("Ola, meu nome e Wilmar")
coleta.group()
# output: 'Wilmar'
```

### Buscando por repetições indefinidas (0 ou 1 até o infinito)

Os símbolos "?", "+" e "*" representam quantidades, isto é, podendo ou não se repetir e uma quantidade X de vezes.

#### Exemplo 1

```python
regex_bat = re.compile(r"Bat(wo)?man")
coleta = regex_bat.search("As aventuras de Batman")
coleta.group()
# output: 'Batman'

coleta = regex_bat.search("As aventuras de Batwoman")
coleta.group()
# output: 'Batwoman'
```


#### Exemplo 2

```python
regex_coringa = re.compile(r"(HA)*")
coleta = regex_coringa.search("HAHAHAHAHA! Esta foi uma excelente piada!")
coleta.group()
# output: 'HAHAHAHAHA'

coleta = regex_coringa.search("HAHA! Esta foi uma excelente piada!")
coleta.group()
# output: 'HAHA'
```

### Comeco e fim de frase

Para buscar um padrão que esteja no início da frase, o símbolo é "^" e o final da frase possui o símbolo "$".

#### Exemplo do começo
```python
regex_inicio = re.compile(r"^Sabia")
coleta = regex_inicio.search("Sabia que o significado da vida, do universo e tudo mais é 42?")
coleta.group()
# output: 'Sabia'
```
#### Exemplo do final
```python
regex_fim = re.compile(r"\d{2}$")
coleta = regex_fim.search("O significado da vida, do universo e tudo mais e 42")
coleta.group()
# output: '42'
```

### Utilizando caractere coringa

O ponto (.) é considerado um caractere coringa, cujo pode substituir qualquer coisa, como espaços, letras, caracteres especiais, etc ...

#### Exemplo 1
```python
regex_coringa = re.compile(".at")
coleta = regex_coringa.findall("The cat with the hat hit a bat")
print(coleta)
# output: ['cat', 'hat', 'bat']
```

#### Exemplo 2
```python
regex_tudo = re.compile(r"Primeiro nome: (.*) Segundo Nome: (.*)")
coleta = regex_tudo.search("Primeiro nome: Harry Segundo Nome: Potter")

coleta.group()
# output: 'Primeiro nome: Harry Segundo Nome: Potter'

coleta.group(1)
# output: 'Harry'

coleta.group(2)
# output: 'Potter'
```

#### Substituição através de padrões
O padrão "\d" representa todo e qualquer número/dígito presente na string.

```python
frase = 'Meu número residencial é (41) 99123-4567 e meu número de celular é (41) 3123-4567'
regex_sub = re.compile(r"\d")
coleta = regex_sub.sub("*", frase)
print(coleta)
# output: 'Meu número residencial é (**) *****-**** e meu número de celular é (**) ****-****'
```
### Separacao e junção através de padrões e substituição
O padrão "\s" representa todo e qualquer espaço presente na string.

```python
frase = 'Meu número residencial é (41) 99123-4567 e meu número de celular é (41) 3123-4567'
regex_sep = re.compile(r"\s")
coleta = regex_sep.split(frase)
print(coleta)
# output: ['Meu', 'número', 'residencial', 'é', '(41)', '99123-4567', 'e', 'meu', 'número', 'de', 'celular', 'é', '(41)', '3123-4567']

coleta = " ".join(coleta)
print(coleta)
# output: 'Meu número residencial é (41) 99123-4567 e meu número de celular é (41) 3123-4567'
```


### Buscando por CPFs
Padrão pronto de RegEx para extrações de CPFs nos variados formatos à estarem presentes.
```python
frase = "O seu CPF é 470.485.110-95 e o meu é 11745629009"
regex_cpf = re.compile(r"\d{3}\.?\d{3}\.?\d{3}\-?\d{2}")
coleta = regex_cpf.findall(frase)
print(coleta)
# output: ['470.485.110-95', '11745629009']
```

### Buscando por telefones
Padrão pronto de RegEx para extrações de números nos variados formatos à estarem presentes.

```python
regex_tel = re.compile(r"\(?\d{2}\)?\s?\d{4,5}\-?\d{4}")
frase = "O seu telefone fixo é (41) 3123-4567, já o celular é 41 99123-4567 e o meu seria 4131234567."
coleta = regex_tel.findall(frase)
print(coleta)
# output: ['(41) 3123-4567', '41 99123-4567', '4131234567']
```