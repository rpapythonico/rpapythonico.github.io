# Bases de Dados - Python

## sqlite

Todo o conceito aplicado aqui foi utilizando o banco de dados sqlite, mas vale destacar que todas as demais **bases relacionais** possuem similaridade com o script executado através da biblioteca sqlite3.

## Exemplo

- Importar a biblioteca

    ```python
    import sqlite3
    ```

- Abrir conexão com um banco de dados

    ```python
    con = sqlite3.connect('example.db')
    ```

- Fechado conexão com um banco de dados

    ```python
    con.close()
    ```

- Abrir cursor em um banco de dados

    O cursor em um banco de dados é o que permite a interatividade entre a linguagem de programação e banco de dados. Permitindo assim, consultas, inserções, exclusões e atualizações nos registros.

    ```python
    cur = con.cursor()
    ```

- Fechar cursor em um banco de dados

    ```python
    cur.close()
    ```

- Criando uma tabela no banco de dados

    ```python
    cur.execute('CREATE TABLE "TB_Cliente"( "CPF" INTEGER NOT NULL UNIQUE, "Nome_Completo" TEXT NOT NULL, "Data_Nascimento" TEXT NOT NULL, "Telefone" TEXT, "Email" TEXT, "CEP" TEXT NOT NULL, PRIMARY KEY("CPF"));')
    ```

- Inserindo um registro no banco de dados

    ```python
    cur.execute("INSERT INTO TB_Cliente VALUES (20955758572, 'Laura Luana Assis', '13/06/1948', '68991361938', 'lauraluanaassis-91@naressi.com.br', '69911355')"))

    con.commit()
    ```
- Inserindo vários registros no banco de dados

    ```python
    lista_registros = [(88190475789, 'José Hugo Manuel Porto', '11/07/1997', '41989320821', 'jjosehugomanuelporto@patriciagrillo.adv.br', '83309270'), (39962955106, 'Marina Carolina dos Santos', '26/09/1995', '81984235792', 'marinacarolinadossantos_@lukin4.com.br', '53350130'), (20955758572, 'Laura Luana Assis', '13/06/1948', '68991361938', 'lauraluanaassis-91@naressi.com.br', '69911355'), (76938977550, 'Yasmin Evelyn Maria Costa', '20/04/1959', '91998657654', 'yasminevelynmariacosta-88@yahoo.com.ar', '66810020'), (25373027375, 'Fernando Giovanni Bernardes', '02/03/1964', '81989889726', 'fernandogiovannibernardes-92@soulcomunicacao.com.br', '51180440'), (85775491947, 'Clarice Vitória Teixeira', '24/02/1958', '82996438794', 'claricevitoriateixeira-97@india.com', '57052605'), (4847726278, 'Kamilly Clara Caldeira', '21/04/1982', '27998331799', 'kamillyclaracaldeira__kamillyclaracaldeira@caferibeiro.com.br', '29194248'), (90123303354, 'Carolina Cláudia Pietra da Rocha', '14/04/1952', '63992520221', 'carolinaclaudiapietradarocha__carolinaclaudiapietradarocha@riguetti.com.br', '77017297'), (96558670801, 'Levi Theo Matheus Ramos', '04/04/1961', '22988505045', 'levitheomatheusramos..levitheomatheusramos@cordeiromaquinas.com.br', '28024123'), (57218723306, 'Davi Márcio Rafael Nogueira', '25/07/1997', '69991521228', 'davimarciorafaelnogueira..davimarciorafaelnogueira@silnave.com.br', '76964042')]

    cur.executemany("INSERT INTO TB_Cliente VALUES (?, ?, ?, ?, ?, ?)", lista_registros)

    con.commit()
    ```

- Apagar registro no banco de dados

    ```python
    cur.execute("DELETE FROM TB_Cliente WHERE CPF = (?)",(88190475789,))

    con.commit()
    ```


- Atualizar registro no banco de dados

    ```python
    cur.execute("UPDATE TB_Cliente SET Telefone = NULL, Email = NULL WHERE CPF = (?)", (39962955106,))

    con.commit()
    ```

- Efetuar consulta no banco de dados

    ```python
    cur.execute("SELECT * FROM TB_Cliente")

    # Para receber UM registro localizado
    cur.fetchone()
    # output: (116415509, 'Analu Julia da Paz', '05/04/1974', '79982386771', 'aanalujuliadapaz@alwan.com.br', '49026130')

    # Para receber TODOS os registros localizados
    cur.fetchall()
    # output: [(116415509, 'Analu Julia da Paz', '05/04/1974', '79982386771', 'aanalujuliadapaz@alwan.com.br', '49026130'), (4847726278, 'Kamilly Clara Caldeira', '21/04/1982', '27998331799', 'kamillyclaracaldeira__kamillyclaracaldeira@caferibeiro.com.br', '29194248'), (7287125803, 'Eduarda Emily Almada', '20/04/1941', '32985692709', 'eduardaemilyalmada_@peopleside.com.br', '36200142')]
    ```