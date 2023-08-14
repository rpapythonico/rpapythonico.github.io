# Openpyxl

## Explicação

A biblioteca Openpyxl é uma das várias bibliotecas disponíveis para trabalhar com Excel dentro do Python e esta, por sua vez, permite realizar a leitura de arquivos tanto no formato ".xlsx" quanto ".xls".

## Comandos

- Instalação da Biblioteca
    ```bash
    pip install openpyxl
    ```
- Importação da Biblioteca
    ```python
    import openpyxl
    ```

- Leitura do arquivo Excel
    ```python
    wb = openpyxl.load_workbook('banca_jornal.xlsx')
    ```

- Apresentação das abas disponíveis para acesso
    ```python
    wb.sheetnames
    # output: ['Planilha1']
    ```

- Seleção da aba para consulta
    ```python
    sheet = wb['Planilha1']
    ```

- Seleção de uma célula específica
    ```python
    sheet['A1'].value
    # output: Chiclete
    sheet['B1'].value
    # output: Barra de Chocolate
    ```


- Apresentação da quantidade de linhas escritas
    ```python
    sheet.max_row
    # output: 6
    ```

- Interação com **todas** as linhas de **uma** coluna
    ```python
    for linha in range(2, sheet.max_row+1):
        nome = sheet.cell(linha, 1).value
        print(nome)
    # output:
    # Chiclete
    # Barra de Chocolate
    # Agua Mineral
    # Jornal
    # Salgadinho
    ```

- Interação com **todas** as linhas de **todas** as colunas
    ```python
    for linha in range(2, sheet.max_row+1):
        nome = sheet.cell(linha, 1).value
        unidade = sheet.cell(linha, 2).value
        valor = sheet.cell(linha, 3).value
        print(f"O produto {nome} teve {unidade} unidade(s) vendida(s) no valor unitário de R$ {valor}")
    # output:
    # O produto Chiclete teve 45 unidade(s) vendida(s) no valor unitário de R$1
    # O produto Barra de Chocolate teve 23 unidade(s) vendida(s) no valor unitário de R$4
    # O produto Agua mineral teve 66 unidade(s) vendida(s) no valor unitário de R$2
    # O produto Jornal teve 4 unidade(s) vendida(s) no valor unitário de R$0.5
    # O produto Salgadinho teve 16 unidade(s) vendida(s) no valor unitário de R$2.5 
    ```

- Fecha o arquivo Excel
    ```python
    wb.close()
    ```