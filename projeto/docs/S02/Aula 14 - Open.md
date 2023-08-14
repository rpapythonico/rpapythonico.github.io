# Open

## Explicação

Outra funcionalidade para manipulação de arquivos é o comando Open. Essa função é nativa de dentro do python, ou seja, não há necessidade de importação. 

Basicamente sua função é abrir (praticamente qualquer) arquivo e conseguir trabalhar com os mesmos.

## Funcionalidades

- Abre arquivo
    ```python
    # open("nome_do_arquivo.ext", "modo de execução")

    # ('r': leitura, 'w': escrita, 'a': acrescentar)

    # Leitura
    arquivo = open(r'log_2022_04_23.txt', 'r')
    # Escrita
    arquivo = open(r'log_2022_04_23.txt', 'w')
    # Acrescentar
    arquivo = open(r'log_2022_04_23.txt', 'a')
    ```

- Escreve no arquivo (modo de execução com "w" ou "a")
    ```python
    arquivo.write('2022_04_23_10:00 - Usuario conectado com sucesso \n')
    ```

- Lê o arquivo (modo de execução com "r")
    ```python
    print(arquivo.read())
    # '2022_04_23_10:00 - Usuario conectado com sucesso \n'
    ```

- Fecha arquivo
    ```python
    arquivo.close()
    ```