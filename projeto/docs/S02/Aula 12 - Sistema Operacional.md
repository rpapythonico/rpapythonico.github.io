# Sistema Operacional

## Explicação

Durante o desenvolvimento, é necessário percorrer diretórios ou realizar ações direto no sistema operacional onde a execução está sendo feita.

Com o Python é possível ter total acesso ao SO, seja ele Windows, MacOS ou Linux.

## Biblioteca - **OS**

A biblioteca OS é a responsavel por trabalhar com o sistema operacional dentro do Python.

### Exemplos

- Importa a Biblioteca
    ```python
    import os
    ```
- Aponta a execução do Python para uma pasta em especifico
    ```python
    os.chdir(r'C:\Users\user\Documents\Code\Python')
    ```

- Localiza a pasta de execução do Python
    ```python
    os.getcwd()
    # output: 'C:\Users\user\Documents\Code\Python'
    ```

- Lista os arquivos presentes na pasta
    ```python
    os.listdir(r'C:\Users\user\Documents\Code\Python')
    # output: ['arquivo_um.txt', 'arquivo_dois.txt', arquivos_tres.txt]
    ```

- Renomeia um arquivo
    ```python
    os.rename('arquivo_teste.txt', 'arquivo_modificado.txt')
    ```


- Remove um arquivo
    ```python
    os.remove('arquivo_modificado.txt')
    ```

## Biblioteca - **glob**

A biblioteca glob é usada para retornar todos os arquivos de um diretorio que foram combinados por um determinado padrão.

### Exemplos

- Instalando a Biblioteca
    ```bash
    pip install glob
    ```

- Importanto a Biblioteca
    ```python
    import glob
    ```
- Buscando arquivos em um diretório através da extensão
    ```python
    glob.glob(r'C:\Users\user\Documents\Code\Python\*.txt')
    # output: ['C:\Users\user\Documents\Code\Python\arquivo_um.txt', 'C:\Users\user\Documents\Code\Python\arquivo_dois.txt', C:\Users\user\Documents\Code\Python\arquivos_tres.txt] 
    ```

## Biblioteca - **Shutil**

Biblioteca voltada à manipulação de arquivos e pastas.

### Exemplos

- Importando a Biblioteca
    ```python
    import shutil
    ```


- Movimenta arquivos entre diretórios
    ```python
    shutil.move(
        r'arquivo_modificado.txt',
        r'.\pasta_move\arquivo_modificado.txt'
        )
    ```

- Copia arquivo de um diretório para outro
    ```python
    shutil.copy(
        r'arquivo_modificado.txt',
        r'.\pasta_move\arquivo_modificado.txt'
        )
    ```
    