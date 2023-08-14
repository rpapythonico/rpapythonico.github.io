# Datetime

## O que é?

Datetime é uma biblioteca interna do Python que permite atuar com datas, tanto pra coleta, quanto pra efetuar operações entre períodos de tempo.

## Exemplo

- Importar a biblioteca:
    
    ```python
    import datetime
    ```
    
- Coletar somente a data:
    
    ```python
    hoje = datetime.date.today()
    # output: datetime.date(2022, 4, 15)
    ```

- Coleta a data e hora do dia vigente:

    ```python
    hoje = datetime.datetime.today()
    # output: datetime.datetime(2022, 4, 15, 23, 17, 18, 892310)
    ```

- Converter a data para um formato visual e no formato string:

    A formatação de data "%d/%m/%Y" e "%Y/%m/%d" usadas nesse exemplo e no abaixo são tiradas diretamente da [documentação](https://docs.python.org/3/library/datetime.html#strftime-and-strptime-format-codes).

    ```python
    hoje_formatado = hoje.strftime('%d/%m/%Y')
    # output: '15/04/2022'
    ```
    
- Retornar a string para o formato datetime:
    
    ```python
    data_antes = datetime.datetime.strptime(hoje_formatado, '%Y/%m/%d')
    # output: datetime.datetime(2022, 4, 15, 0, 0)
    ```


- Trazer a data de ontem ou de amanhã:

    No uso do timedelta para calcular o dia anterior ou sucessor, é importante frisar que o símbolo de "+" é quem dita se irá operar pro passado ou futuro.
    
    ```python
    # Dia anterior
    ontem = hoje - datetime.timedelta(days=1)
    # output: datetime.datetime(2021, 4, 14, 23, 17, 18, 892310)

    # Dia seguinte
    amanha = hoje + datetime.timedelta(days=1)
    # output: datetime.datetime(2021, 4, 16, 23, 17, 18, 892310)
    ```
    
- Calcular a diferença de dias de uma data para outra:
    
    ```python
    (amanha - ontem).days
    # output: 2
    ```
