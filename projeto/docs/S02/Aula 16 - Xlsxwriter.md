# Xlsxwriter

## Explicação

O Python também permite criar excel do zero, que é o caso da "lib" xlsxwriter, que é geralmente utilizada para a criação de relatórios.

Conforme o nome da biblioteca diz, ela apenas serve para escrever excel, não sendo possível realizar a leitura. Isto é, ela irá sobrescrever informações se já tiver algum dado no arquivo.

## Comandos

- Instalação da biblioteca
    ```bash
    pip install XlsxWriter
    ```

- Importação da biblioteca
    ```python
    from xlsxwriter import Workbook
    ```
    
- Criação e abertura do arquivo Excel
    ```python
    wb = Workbook('livros.xlsx')
    ```

- Criação de aba no Excel
    ```python
    planilha = wb.add_worksheet('Livros')
    ```

- Criação do cabeçalho com letras em negrito
    ```python
    bold = wb.add_format({'bold':1})
    planilha.write('A1', 'Nome', bold)
    planilha.write('B1', 'Autor', bold)
    planilha.write('C1', 'Data Lançamento', bold)
    planilha.write('D1', 'Pais de Origem', bold)
    planilha.write('E1', 'Genero', bold)
    ```


- Criação de lista contendo tuplas com os dados a serem cadastrados
    ```python
    livros = [('Harry Potter e a Pedra Filosofal ', 'J. K. Rowling', '26/07/1997', 'Inglaterra', 'Aventura/Fantasia'), ('Jogos Vorazes','Suzanne Collins', '14/09/2008', 'Estados Unidos', 'Aventura'),('Percy Jackson o Ladrao de Raios', 'Rick Riordan', '28/07/2005', 'Estados Unidos', 'Mitologia grega'), ('O Nevoeiro', 'Stephen King', '01/01/1980', 'Estados Unidos', 'Terror Psicologico'), ('Contos de Grimm', 'Jacob Grimm / Wilhelm Grimm', '20/12/1812', 'Alemanha', 'Contos de fadas')]
    ```

- Escrita dos dados no arquivo Excel
    ```python
    row, col = 1, 0
    for livro in livros:
        sheet.write_string(row, col, livro[0])
        sheet.write_string(row, col+1, livro[1])
        sheet.write_string(row, col+2, livro[2])
        row += 1
    ```

- Salvando e fechando o arquivo Excel
    ```python
    wb.close()
    ```