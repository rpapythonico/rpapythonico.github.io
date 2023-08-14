# Aula 3 - Funções, Manipulações e Erros

## Funções:

- def():
    - Ex.:
        
        ```python
        def soma(num1, num2):
        	return num1 + num2
        ```
        

## Manipulação de String:

- Indexação e slicing [:]:
    - Ex.:
        
        ```python
        frase = 'Python é a melhor linguagem do mundo'
        
        frase[:6]
        # output: 'Python'
        
        frase[31:]
        # output: 'mundo'
        
        frase[:]
        # output: 'Python é a melhor linguagem do mundo'
        ```
        
- .find():
    - Ex.:
        
        ```python
        frase.find('mundo')
        # output: 31
        ```
        
- None e vazio:
    - Apaga o valor de dentro de uma variável.
    - Ex.:
        
        ```python
        frase = None
        ```
        
- in e not in
    - Ex.:
        
        ```python
        frase = 'Python é a melhor linguagem do mundo'
        
        'Python' in frase
        # output: True
        
        'Python' not in frase
        # output: False
        ```
        
- upper() e isupper()
    - Ex.:
        
        ```python
        frase = 'Python é a melhor linguagem do mundo'
        
        frase.isupper()
        # output: False
        
        frase.upper()
        # output: 'PYTHON É A MELHOR LINGUAGEM DO MUNDO'
        ```
        
- lower() e islower()
    - Ex.:
        
        ```python
        frase = 'PYTHON É A MELHOR LINGUAGEM DO MUNDO'
        
        frase.islower()
        # output: False
        
        frase.lower()
        # output: 'python é a melhor linguagem do mundo'
        ```
        
- startswith() e endswith()
    - Ex.:
        
        ```python
        frase = 'Python é a melhor linguagem do mundo'
        
        frase.startswith('Python')
        # output: True
        
        frase.endswith('mundo')
        # output: True
        ```
        
- split() e join()
    - Ex.:
        
        ```python
        frase = 'Python é a melhor linguagem do mundo'
        
        frase = palavra.split(' ')
        # output: ['Python', 'é', 'a', 'melhor', 'linguagem', 'do', 'mundo']
        
        ';'.join(frase)
        #output: 'Python;é;a;melhor;linguagem;do;mundo'
        ```
        
- rjust(), ljust() e center():
    - Ex.:
        
        ```python
        frase = 'Python é a melhor linguagem do mundo'
        
        frase.rjust(50,'-')
        # output: '--------------Python é a melhor linguagem do mundo'
        
        frase.ljust(50,'-')
        # output: 'Python é a melhor linguagem do mundo--------------'
        
        frase.center(50,'*')
        # output: '*******Python é a melhor linguagem do mundo*******'
        ```
        
- zfill():
    - Ex.:
        
        ```python
        cpf = '345678911'
        
        cpf.zfill(11)
        # output: '00345678911'
        ```
        
- strip(), rstrip() e lstrip():
    - Ex.:
        
        ```python
        nome = '          Harry Potter          '
        
        nome.strip()
        # output: 'Harry Potter'
        
        nome.rstrip()
        # output: '          Harry Potter'
        
        nome.lstrip()
        # output: 'Harry Potter          '
        ```
        
- replace():
    - Ex.:
        
        ```python
        frase = 'Java é a melhor linguagem do mundo'
        
        frase.replace('Java', 'Python')
        # output: 'Python é a melhor linguagem do mundo'
        ```
        

## Exceções/Erros:

- try:, except:, else: e finally:
    - Ex.:
        
        ```python
        def divisao(valor1, valor2):
          valor1 = str(valor1)
          try: # É a etapa de tentativa. Se der sucesso, vai para o "else" e se der erro, irá para o "except"
            valor1 = int(valor1)
            valor2 = int(valor2)
          except ZeroDivisionError as error: # Trata o erro de divisão por zero somente
            print(f'{error}')
            print(f'Não foi possível dividir o valor {valor1} pelo valor {valor2}')
        	except: # Trata qualquer erro que não esteja mapeado
        		print('Erro desconhecido e ele poderia ter parado o programa!')
          else: # Se tudo der certo dentro do "try", o código continuará aqui
            return valor1 / valor2
          finally: # Essa ação abaixo será executada independente de sucesso ou erro
            print('Isso aqui rodará independente do erro')
        
        num1= 25
        num2 = 0
        
        divisao(num1, num2)
        # output: 'Não foi possível dividir o valor 25 pelo valor 0'
        ```
        
- raise:
    - Ex.:
        
        ```python
        raise BaseException('Este é um erro personalizado caso caia em alguma condicional inválida!')
        # output: Traceback (most recent call last):
        #  File "<pyshell#27>", line 1, in <module>
        #    raise BaseException('Este é um erro personalizado caso caia em alguma condicional inválida!')
        # BaseException: Este é um erro personalizado caso caia em alguma condicional inválida!
        ```
        
- Tipos de erros: [https://www.programiz.com/python-programming/exceptions#built-in](https://www.programiz.com/python-programming/exceptions#built-in)

## datetime:

- Importar a biblioteca:
    
    ```python
    import datetime
    ```
    
- Pegar a data ou data e hora do dia vigente:
    
    ```python
    hoje = datetime.date.today()
    # output: datetime.date(2021, 10, 27)
    
    #ou
    
    hoje = datetime.datetime.today()
    # output: datetime.datetime(2021, 10, 27, 0, 6, 56, 978062)
    ```
    
- Converter a data para um formato visual e no formato string:
    
    ```python
    hoje_formatado = hoje.strftime('%d/%m/%Y')
    # output: '27/10/2021'
    ```
    
- Retornar a string para o formato datetime:
    
    ```python
    data_antes = datetime.datetime.strptime(hoje_formatado, '%Y/%m/%d')
    # output: datetime.datetime(2021, 10, 27, 0, 0)
    ```
    
- Trazer a data de ontem ou de amanhã:
    
    ```python
    # Dia anterior
    ontem = hoje - datetime.timedelta(days=1)
    # output: datetime.datetime(2021, 10, 26, 0, 6, 56, 978062)
    
    # Dia seguinte
    amanha = hoje + datetime.timedelta(days=1)
    # output: datetime.datetime(2021, 10, 28, 0, 6, 56, 978062)
    ```
    
- Calcular a diferença de dias de uma data para outra:
    
    ```python
    (amanha - ontem).days
    # output: 2
    ```
    

## Extras:

Documentação datetime: [https://docs.python.org/pt-br/3/library/datetime.html](https://docs.python.org/pt-br/3/library/datetime.html)

Tabela de símbolos para o strftime: [https://www.programiz.com/python-programming/datetime/strftime#format-code](https://www.programiz.com/python-programming/datetime/strftime#format-code)