# Aula 7 - RegEx e APIs

## Testar RegEx:

- [https://pythex.org/](https://pythex.org/)
- [https://regex101.com/](https://regex101.com/)
- [https://www.regexpal.com/](https://www.regexpal.com/)
- [https://regexr.com/](https://regexr.com/)

## re:

- Importar biblioteca:
    
    ```python
    import re
    ```
    
- Criar padrão do RegEx à ser procurado:
    
    ```python
    tel_regex = re.compile(r'\(\d\d\) \d\d\d\d\d\-\d\d\d\d')
    ```
    
- Buscar correspondência na string inteira:
    
    ```python
    coleta = tel_regex.search('Meu número é (41) 99123-4567')
    ```
    
- Coletar a única combinação completa:
    
    ```python
    print(coleta.group(0))
    # output: (41) 99123-4567
    ```
    
- Fazer grupos com parênteses:
    
    ```python
    grupos_regex = re.compile(r'(\d{2}) (\d{4,5})\-(\d{4})')
    coleta = grupos_regex.search('Meu número é 41 99123-4567')
    ```
    
- Coletar dados dos grupos encapsulados pelo parênteses:
    
    ```python
    # Usando index
    print(f'Este é o grupo 0: {coleta.group(0)}')
    # output: 41 99123-4567
    
    print(f'Este é o grupo 1: {coleta.group(1)}')
    # output: 41
    
    print(f'Este é o grupo 2: {coleta.group(2)}')
    # output: 99123
    
    print(f'Este é o grupo 3: {coleta.group(3)}')
    # output: 4567
    
    # Tupla com os valores dos grupos
    coleta.groups()
    # output: ('41', '99123', '4567')
    ```
    
- Selecionar uma palavra ou outra:
    
    ```python
    regex_ou = re.compile('Wilber|Thomas')
    
    coleta = regex_ou.search('Olá, meu nome é Wilber')
    
    print(coleta.group())
    # output: Wilber
    
    coleta = regex_ou.search('Olá, meu nome é Thomas')
    
    print(coleta.group())
    # output: Thomas
    ```
    
- Selecionar parcialmente uma palavra ou outra:
    
    ```python
    regex_ou = re.compile('Wil(ber|mar)')
    
    coleta = regex_ou.search('Olá, meu nome é Wilber')
    
    print(coleta.group())
    # output: Wilber
    
    coleta = regex_ou.search('Olá, meu nome é Wilmar')
    
    print(coleta.group())
    # output: Wilmar
    ```
    
- Elemento opcional no meio de uma palavra/frase (existe ou não existe):
    
    ```python
    regex_bat = re.compile(r'Bat(wo)?man')
    
    coleta = regex_bat.search('As aventuras de Batman')
    
    print(coleta.group())
    # output: Batman
    
    coleta = regex_bat.search('As aventuras da Batwoman')
    
    print(coleta.group())
    # output: Batwoman
    ```
    
- Repetição indefinida (0 ou 1 até o infinito):
    
    ```python
    # 0 até o infinito
    regex_risada = re.compile(r'(HA)*')
    
    # 1 até o infinito
    regex_risada = re.compile(r'(HA)+')
    
    coleta = regex_risada.search('HAHAHAHAHA! Está foi uma excelente piada!')
    
    print(coleta.group())
    # output: HAHAHAHAHA
    ```
    
- Localizar mais de uma correspondência (resultado em lista):
    
    ```python
    tel_regex = re.compile(r'\(\d{2}\) \d{4,5}\-\d{4}')
    
    coleta = tel_regex.findall('Meu número residencial é (41) 99123-4567 e meu número de celular é (41) 3123-4567')
    
    print(coleta)
    # output: ['(41) 99123-4567', '(41) 3123-4567']
    ```
    
- Correspondência no início da frase/texto:
    
    ```python
    regex_inicio = re.compile(r'^Sabia')
    
    coleta = regex_inicio.search('Sabia que o significado da vida, do universo e tudo mais é 42?')
    
    print(coleta.group())
    # output: Sabia
    ```
    
- Correspondência no final da frase/texto:
    
    ```python
    regex_inicio = re.compile(r'\d{2}$')
    
    coleta = regex_inicio.search('O significado da vida, do universo e tudo mais é 42')
    
    print(coleta.group())
    # output: 42
    ```
    
- Caractere coringa:
    
    ```python
    regex_coringa = re.compile(r'.at')
    
    coleta = regex_coringa.findall('The cat with the hat hit a bat')
    
    print(coleta)
    # output: ['cat', 'hat', 'bat']
    ```
    
- Correspondência sem saber a palavra, mas tendo uma frase padrão:
    
    ```python
    regex_tudo = re.compile(r'Primeiro nome: (.*) Segundo Nome: (.*)')
    
    coleta = regex_tudo.search('Primeiro nome: Harry Segundo Nome: Potter')
    
    print(coleta.group(1))
    # output: Harry
    
    print(coleta.group(2))
    # output: Potter
    ```
    
- Remover Case Sensitive (diferença entre maiúsculas e minúsculas) do RegEx:
    
    ```python
    regex_cases = re.compile(r'metallica', re.IGNORECASE)
    
    coleta = regex_cases.search('METALLICA é uma banda de muito sucesso!')
    
    print(coleta.group())
    # output: METALLICA
    ```
    
- Substituir valores:
    
    ```python
    regex_sub = re.compile(r'\d')
    
    coleta = regex_sub.sub('*', 'Meu número residencial é (41) 99123-4567 e meu número de celular é (41) 3123-4567')
    
    print(coleta)
    # output: Meu número residencial é (**) *****-**** e meu número de celular é (**) ****-****
    ```
    
- Separar uma frase através de um padrão:
    
    ```python
    regex_separador = re.compile(r'\s')
    
    coleta = regex_separador.split('METALLICA é uma banda de muito sucesso!')
    
    print(coleta)
    # output: ['METALLICA', 'é', 'uma', 'banda', 'de', 'muito', 'sucesso!']
    ```
    
- Padrões prontos:
    - Buscar por CPF:
        
        ```python
        regex_cpf = re.compile(r'\d{3}\.?\d{3}\.?\d{3}\-?\d{2}')
        
        coleta = regex_cpf.findall('O seu CPF é 470.485.110-95 e o meu é 11745629009')
        
        print(coleta)
        # output: ['470.485.110-95', '11745629009']
        ```
        
    - Busca por telefone:
        
        ```python
        regex_tel = re.compile(r'\(?\d{2}\)?\s?\d{4,5}\-?\d{4}')
        
        coleta = regex_tel.findall("O seu telefone fixo é (41) 3123-4567, já o celular é 41 99123-4567 e o meu seria 4131234567.")
        
        print(coleta)
        # output: ['(41) 3123-4567', '41 99123-4567', '4131234567']
        ```
        
    - Busca por Email:
        
        ```python
        regex_email = re.compile(r'(?:\w+\.)*\w*\@\w*(?:\.\w+)+')
        
        coleta = regex_email.findall('O seu e-mail é tiara.hessel9@yahoo.com, o meu e-mail é shaun_nitzsche96@hotmail.com e acredito que podemos criar um e-mail em conjunto chamado alphonso19@outlook.com.br.')
        
        print(coleta)
        # output: ['tiara.hessel9@yahoo.com', 'shaun_nitzsche96@hotmail.com', 'alphonso19@outlook.com.br']
        ```
        

## APIs:

- **REST:**
    - Postman: [https://www.postman.com/downloads/](https://www.postman.com/downloads/)
    - Insomnia: [https://insomnia.rest/download](https://insomnia.rest/download)
- **SOAP:**
    - SoapUI: [https://www.soapui.org/downloads/soapui/](https://www.soapui.org/downloads/soapui/)

**Bibliotecas:**

- requests
- json

**Funcionalidades:**

- **GET**
    - API de teste:
        
        ```python
        import requests
        
        url = "https://reqres.in/api/users?page=2"
        
        response = requests.get(url)
        
        r_json = response.json()
        
        print(r_json['data'][0]['email'])
        # output: michael.lawson@reqres.in
        ```
        
    - API de Universidades no Brasil:
        
        ```python
        import requests
        
        url = "http://universities.hipolabs.com/search?country=brazil"
        
        response = requests.get(url)
        
        r_json = response.json()
        
        print(r_json[15]['name'])
        # output: Universidade Regional de Blumenau
        ```
        
    - Exemplos GET:
        - [https://viacep.com.br/](https://viacep.com.br/)
        - [https://jsonplaceholder.typicode.com/](https://jsonplaceholder.typicode.com/)
        - [https://www.bcb.gov.br/api/servico/sitebcb/indicadorinflacao](https://www.bcb.gov.br/api/servico/sitebcb/indicadorinflacao)
        - [https://agify.io/](https://agify.io/)
        - https://github.com/Hipo/university-domains-list
- **POST:**
    - Cadastrar usuário de teste:
        
        ```python
        import requests
        import json
        
        url = "https://reqres.in/api/users"
        
        payload = json.dumps({
          "name": "Harry Potter",
          "job": "Desenvolvedor RPA"
        })
        headers = {
          'Content-Type': 'application/json'
        }
        
        response = requests.post(url, headers=headers, data=payload)
        
        r_json = response.json()
        
        print(r_json['job'])
        # output: Desenvolvedor RPA
        ```
        
- PUT:
    - Serve para atualizar algum dado em base através de API.
- DELETE:
    - Serve para apagar algum dado em base através de API.

## Extras:

### APIs para "Brincar":

- [https://apipheny.io/free-api/](https://apipheny.io/free-api/)
- https://github.com/public-apis/public-apis
- [https://jsonplaceholder.typicode.com/](https://jsonplaceholder.typicode.com/)
- [https://reqres.in/](https://reqres.in/)
- [https://gorest.co.in/](https://gorest.co.in/)

### Aprender RegEx:

- [https://docs.python.org/3/library/re.html](https://docs.python.org/3/library/re.html)
- [https://www.w3schools.com/python/python_regex.asp](https://www.w3schools.com/python/python_regex.asp)
- [https://medium.com/xp-inc/regex-um-guia-pratico-para-express%C3%B5es-regulares-*1ac5fa4dd39f*](https://medium.com/xp-inc/regex-um-guia-pratico-para-express%C3%B5es-regulares-1ac5fa4dd39f)
- [https://digitalinnovation.one/artigos/regex-regular-expression-ou-expressao-regular](https://digitalinnovation.one/artigos/regex-regular-expression-ou-expressao-regular)
- [https://cheatography.com/davechild/cheat-sheets/regular-expressions/](https://cheatography.com/davechild/cheat-sheets/regular-expressions/)