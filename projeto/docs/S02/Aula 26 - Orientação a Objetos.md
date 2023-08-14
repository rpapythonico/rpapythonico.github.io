# Orientação a Objetos

## O que é?

Considerada um paradigma da programação, a mesma vem com intuito de inovar o conceito de **programação estruturada** que é basicamente o que foi feito até agora no curso. Ou seja, foi trabalhado com o conceito de execução sequencial, onde o código é escrito e executado de cima pra baixo (top-down).

A Orientação a Objetos propõe trabalhar com entidades/objetos. Isto é, um sistema pode ser particionado no conceito base das características\atributos dele (def \_\_init\_\_()) e suas funcionalidades internas (defs).

Essa abordagem visa:
1. Aprimorar o controle de acesso às variáveis;
2. Permitir o reuso de funções;
3. Permitir fácil manutenção/legibilidade.

## Exemplo

1. Criando um arquivo

    Para poder começar uma codificação Orientada a Objetos, é necessário criar um arquivo com a extensão ".py" contendo o nome do que virá à ser o objeto.

    Ex.: **carro.py**

2. Instanciando uma classe:

    A classe é a que receberá todos os atributos e funcionalidades à serem realizados dentro daquele escopo específico no projeto. O nome da classe é basedo no que ela fará e será escrita em PascalCase (as palavras compostas ou frases deverão ser sem espaços e cada palavra deverá começar com a letra maiúscula).

    ```python
    class Carro:
    ```

3. Criar os atributos da classe:

    Nessa etapa serão recebidos os atributos do objeto e é aqui que podem ser postos funções específicas que devem ser realizadas sempre que a classe criada for chamada e tiver seus parâmetros informados.

    ```python
    def __init__(self, fabricante, modelo, ano=2022):
        self.fabricante = fabricante.title()
        self.modelo = modelo.title()
        self.ano = int(ano)
        self.odometro = 0
    ```

4. Criar métodos na classe:

    Todas as funcionalidades da classe serão postas aqui. Nesse caso se trata de um carro e o mesmo terá como foco as funcionalidades referente a sua quilometragem rodada.

    ```python
    def nome_descritivo(self):
        print(f"O carro é do ano {self.ano}, foi fabricado pelo(a) {self.fabricante} e seu modelo é {self.modelo}.")

    def apresenta_odometro(self):
        print(f"O carro possui {self.odometro} quilômetros rodados.")

    def atualiza_odometro(self, kms):
        if kms >= self.odometro:
            self.odometro = kms
        else:
            print("Não é possível diminuir a quilometragem rodada.")

    def incrementa_odometro(self, kms):
        self.odometro += kms
    ```

5. Importando uma classe criada:

    Para importar uma classe corretamente, é necessário estar executando o script de Python no mesmo diretório em que ela se encontra. Isso pode ser realizado ao abrir a pasta em um ambiente de trabalho na IDE ou usando o comando "os.chdir()" para dizer em qual diretório está a classe.

    ```python
    from carro import Carro
    ```

6. Criando um objeto da classe:

    ```python
    obj = Carro("Ford", "Ka", 2021)
    ```

7. Acessando uma função da classe:

    ```python
    obj.apresenta_odometro()
    # output: O carro possui 0 quilômetros rodados.
    ```

8. Atualizando um valor da classe:

    ```python
    obj.atualiza_odometro(1500)
    # output: O carro possui 0 quilômetros rodados.
    ```

9. Acessando algum atributo da classe:
    ```python
    obj.ano
    # output: 2021
    ```