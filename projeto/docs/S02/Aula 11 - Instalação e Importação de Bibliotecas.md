# Pacotes

## Explicação - **Pacotes**

O Python é carregado de funcionalidades que já permitem criar alguns scripts, mas em determinado momento, faz-se necessário obter algumas funções extras (muitas vezes criadas pela própria comunidade).

Para isso, será utilizado o [**pip**](https://pypi.org/project/pip/). O mesmo é um gerenciador de pacotes, que permite instalar, atualizar e remover pacotes. Todas as bibliotecas instaláveis estão disponíveis no [**portal PyPI**](https://pypi.org/).

Obs.¹: O **pip** já vem embarcado com o Python durante a instalação no equipamento (exceto para usuários do Sistema Operacional Linux).

Obs.²: Todas as bibliotecas são devidamente baixadas diretamente no diretório em que foi instalado o Python.

## Exemplos - **pip**

**Todos os comandos a seguir deverão ser realizados via Terminal/CMD/Bash/Shell.**

- Para instalar uma biblioteca:
    ```bash
    pip install xlrd
    ```

- Para desinstalar uma biblioteca:
    ```bash
    pip uninstall xlrd
    ```

- Exportar todos os pacotes instalados:
    ```bash
    pip freeze > requirements.txt
    ```

- Importar todos os pacotes anteriormente extraídos:
    ```bash
    pip install -r requirements.txt
    ```
    

## Exemplos - **import**

**Todos os comandos a seguir deverão ser realizados na IDE em que será escrito o código.**

- Importar a biblioteca com todas as funções:
    ```python
    import xlrd
    ```

- Importar a biblioteca com "apelido":
    ```python
    import pandas as pd
    ```

- Importar uma função específica de dentro da biblioteca:
    ```python
    from time import sleep
    ```