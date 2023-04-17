Criando a chave estrangeira ligando a tabela de PRODUTOS com a tabela de ITENS_NOTAS através do campo CODIGO e outra ligação entre a tabela VENDAS e ITENS_NOTAS através do campo NUMERO.

```
USE vendas_sucos;
```

```
ALTER TABLE itens_notas ADD CONSTRAINT FK_VENDAS
FOREIGN KEY (NUMERO)
REFERENCES VENDAS (NUMERO);

ALTER TABLE itens_notas ADD CONSTRAINT FK_PRODUTOS
FOREIGN KEY (CODIGO)
REFERENCES PRODUTOS (CODIGO);

```