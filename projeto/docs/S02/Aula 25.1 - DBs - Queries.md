# Bases de Dados - Queries

## Query para criação de tabela

```sql
CREATE TABLE TB_NomeDesejado
```

## Query para inserir registro(s)

```sql
INSERT INTO TB_NomeTabela (coluna1, coluna2, coluna3)
VALUES (valor1, valor2, valor3)
```

## Query para deletar registro(s)
```sql
DELETE FROM TB_NomeTabela
WHERE coluna = valor
```
## Query para atualizar registro(s)
```sql
UPDATE TB_NomeTabela
SET coluna = valorY
WHERE coluna = valorX
```
## Query para efetuar consulta(s)
```sql
SELECT *
FROM TB_NomeTabela
-- Onde * representa todas as colunas
```