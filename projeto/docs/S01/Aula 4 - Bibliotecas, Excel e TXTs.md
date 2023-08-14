# Aula 4 - Bibliotecas, Excel e TXTs

## Bibliotecas:

- Repositório das Bibliotecas: [https://pypi.org/](https://pypi.org/)
- Comando para instalar bibliotecas externas:
    
    ```bash
    pip install nome_da_biblioteca
    # Ex.: pip install openpyxl
    ```
    
- Comando para usar biblioteca no código
    
    ```python
    # Importa a biblioteca com todas as funções dela
    import nome_da_biblioteca
    # import xlrd
    
    # Importa a biblioteca e permite criar um "apelido" pra ela
    import nome_da_biblioteca as ndb
    # Ex.: import pandas as pd
    
    # Importa uma função específica de dentro da biblioteca
    from nome_da_biblioteca import funcao
    # Ex.: from time import sleep
    ```
    

## Manipulação de Arquivos:

- Abrir o arquivo:
    - Para criar:
        
        ```python
        arqv = open('nome_do_arquivo.txt', 'w')
        ```
        
    - Para ler:
        
        ```python
        arqv = open('nome_do_arquivo.txt', 'r')
        ```
        
    - Para continuar um texto:
        
        ```python
        arqv = open('nome_do_arquivo.txt', 'a')
        ```
        
- Escrever dentro do .txt:
    
    ```python
    arqv.write('texto do arquivo')
    ```
    
- Fechar o arquivo:
    
    ```python
    arqv.close()
    ```
    

## **Interação com o SO:**

- os:
    - Importar a biblioteca:
        
        ```python
        import os
        ```
        
    - Renomear um arquivo:
        
        ```python
        os.rename('arquivo_teste.txt', 'arquivo_modificado.txt')
        ```
        
    - Remover um arquivo da pasta:
        
        ```python
        os.remove('arquivo_modificado.txt')
        ```
        
    - Listar os arquivos presentes na pasta:
        
        ```python
        os.listdir('.')
        ```
        
    - Aponta a execução do Python para uma pasta em específico:
        
        ```python
        os.chdir('')
        ```
        
- glob:
    - Importar a biblioteca:
        
        ```python
        import glob
        ```
        
    - Listar arquivos do diretório pela sua extensão:
        
        ```python
        glob.glob(r'.\*.txt')
        ```
        
- shutil:
    - Importar a biblioteca:
        
        ```python
        import shutil
        ```
        
    - Movimentar um arquivo para outra pasta:
        
        ```python
        shutil.move('arquivo_modificado.txt', r'.\pasta_move\arquivo_modificado.txt')
        ```
        
    - Copiar um arquivo para outra pasta:
        
        ```python
        shutil.copy(r'.\pasta_move\arquivo_modificado.txt', r'.\arquivo_modificado_copy.txt')
        ```
        

## **Bibliotecas Excel:**

### xlrd;

- Importar a biblioteca:
    
    ```python
    import xlrd
    ```
    
- Abre um arquivo Excel (XLS):
    
    ```python
    wb = xlrd.open_workbook('banca_jornal.xls')
    ```
    
- Seleciona a aba do Excel:
    
    ```python
    sheet = wb.sheet_by_name('Planilha1')
    ```
    
- Pega valores da primeira coluna:
    
    ```python
    for cell in sheet.col(0):
    	cell
    ```
    

### openpyxl;

- Importa a biblioteca:
    
    ```python
    import openpyxl
    ```
    
- Abrir um arquivo Excel (XLS ou XLSX):
    
    ```python
    wb = openpyxl.load_workbook('banca_jornal.xlsx')
    ```
    
- Apresenta o nome de todas as abas do Excel aberto:
    
    ```python
    wb.get_sheet_names()
    # output: ['Planilha1']
    ```
    
- Seleciona a aba do Excel:
    
    ```python
    sheet = wb['Planilha1']
    ```
    
- Ler o valor da primeira célula (A1):
    
    ```python
    sheet['A1'].value
    # output: Chiclete
    ```
    
- Apresentar números de linhas:
    
    ```python
    sheet.max_row
    # output: 6
    ```
    
- Percorre uma coluna inteira do Excel:
    
    ```python
    # Nesse código, ele não irá pegar o cabeçalho da tabela
    # Caso queira pegar o cabeçalho, basta trocar o número 2 pelo número 1
    for linha in range(2, sheet.max_row+1):
    	nome = sheet.cell(linha, 1)
    
    # output:
    # Chiclete
    # Barra de Chocolate
    # Agua mineral
    # Jornal
    # Salgadinho
    ```
    
- Pegar valores das três colunas, passando por todas as linhas:
    
    ```python
    for linha in range(2, sheet.max_row+1):
    	nome = sheet.cell(linha, 1).value
    	unidade = sheet.cell(linha, 2).value
    	valor = sheet.cell(linha, 3).value
    	print(f'O produto {nome*} teve* {unidade} unidades vendidas no valor unitário de R${valor}')
    
    # output:
    # O produto Chiclete foi teve 45 unidades vendidas no valor unitário de R$1
    # O produto Barra de Chocolate foi teve 23 unidades vendidas no valor unitário de R$4
    # O produto Agua mineral foi teve 66 unidades vendidas no valor unitário de R$2
    # O produto Jornal foi teve 4 unidades vendidas no valor unitário de R$0.5
    # O produto Salgadinho foi teve 16 unidades vendidas no valor unitário de R$2.5
    ```
    
- Fechar o arquivo Excel:
    - 

### pandas:

- Importar a biblioteca:
    
    ```python
    import pandas as pd
    ```
    
- Ler arquivo Excel:
    
    ```python
    df = pd.read_excel('banca_jornal.xlsx')
    ```
    
- Selecionar uma coluna:
    
    ```python
    df['Produto']
    ```
    
- Apresenta as abas disponíveis do Excel:
    
    ```python
    pd.ExcelFile.sheet_names
    ```
    

### xlsxwriter:

- Importar a biblioteca:
    
    ```python
    import xlsxwriter
    ```
    
- Criar arquivo Excel:
    
    ```python
    wb = xlsxwriter.Woorkbook('alunos.xlsx')
    ```
    
- Criar aba no arquivo Excel:
    
    ```python
    ws = wb.add_worksheet('Planilha')
    ```
    
- Colocar palavras em Negrito:
    
    ```python
    bold = wb.add_format({'bold':1})
    ```
    
- Escreve cabeçalho em negrito no Excel:
    
    ```python
    ws.write('A1', 'Nome', bold)
    ws.write('B1', 'Idade', bold)
    ws.write('C1', 'Cidade', bold)
    ```
    
- Cria valores para serem adicionados em formato de tabela:
    
    ```python
    alunos = [('Thomas', '24', 'Curitiba'), ('Fernanda', '12', 'Sao Paulo'), ('Augusto', '56', 'Rio de Janeiro'), ('Marcela', '22', 'Maringa')]
    ```
    
- Looping para escrever valores em formato de tabela:
    
    ```python
    row = 1
    col = 0
    
    for aluno in alunos:
    	ws.write_string(row, col, aluno[0])
    	ws.write_string(row, col+1, aluno[1])
    	ws.write_string(row, col+2, aluno[2])
    	row += 1
    ```
    
- Fechar e salvar o arquivo Excel:
    
    ```python
    wb.close()
    ```
    

## Extras:

### **Caracteres especiais:**

![escape_caracter.png](../img/escape_caracter.png)

- **Outras opções:** [https://www.python-excel.org/](https://www.python-excel.org/)