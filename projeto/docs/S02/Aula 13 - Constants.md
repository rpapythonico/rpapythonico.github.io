# Constants

## Explicação

Constantes são variaveis que percorrem todo o codigo tendo o mesmo valor. 

Para isso,  basta criar um arquivo, digitar os valores desejados e em seguida realizar a importação dessas informações dentro do(s) código(s) desejado(s).

## Nomenclatura

A regra para essas variáveis é de SCREAMING_SNAKE_CASE (todas as letras maiúsculas).

Ex:.
```python
LOGIN_USER = "username"
LOGIN_PASS = "password"
```

## Exemplo - Criação do arquivo

1. Gera um arquivo com extensão ".py";
    - Ex.: `constants.py`
2. Instancia as variáveis utilizando letras maiúsculas e atribui os devidos valores.
    - Ex.:
        ```python
        LOGIN_USER = "RPA_PYTHONICO"
        LOGIN_PASS = "SENHA@123"
        ```

## Exemplo - Importação do arquivo

1. Após criado o arquivo, basta importar o mesmo dentro de qualquer código em python;
    ```python
    import sys
    # Comando responsavel por adiconar um caminho dentro do codigo.
    # Assim o python consegue identificar o arquivo e importar o mesmo.
    sys.path.append(r'CAMINHO ONDE ESTA LOCALIZADA NOSSA CONSTANTS')
    import constants as const
    ```


2. Com as variáveis importadas, basta usá-las.
    ```python
    print(const.LOGIN_USER)
    # output: "RPA_PYTHONICO"
    print(const.LOGIN_PASS)
    # output: "SENHA@123"
    ```