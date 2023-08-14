# CSV

## Explicação

Assim como os formatos xlsx e xls, também é possível ler arquivos gerados por programas ou sites que possuem os valores separadas por delimitadores. 

## CSV

- Utilizando a biblioteca CSV, é possível ler e escrever arquivos  no formato ".csv".

    - **Importação**:
        ```python
        import csv
        ```
    
    - **Exemplo de leitura de um arquivo csv**:
        ```python
        import csv
        # Abertura do arquivo csv.
        csv_file = open('tabela_clientes.csv')
        # Leitura dos dados
        ## Importante informar o delimiter corretamente, pois ele que é responsavel pela quebra das informações
        arquivo = csv.reader(csvfile, delimiter=',')
        # Dentro da variavel arquivo ficou armazenado uma lista de tuplas contendo todos os dados do csv
        for linha in arquivo:
            # Com o for percorremos por todas as tuplas da lista, e conseguimos categorizar todos os elementos
            cpf = linha[0]
            nome = linha[1]
            data_nascimento = linha[2]
            telefone = linha[3]
            email = linha[4]
            cep = linha[5]
        print(cpf, nome, data_nascimento, telefone, email, cep)
        # output: '99070950600' 'Jorge Bernardo Teixeira' '22/07/1948' '82981039094' 'jjorgebernardoteixeira@unimedrio.com.br' '57010364'
        ```

