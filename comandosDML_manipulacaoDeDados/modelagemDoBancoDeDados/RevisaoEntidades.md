- um banco MySQL possui dentro da sua estrutura do seu servidor um conjunto de uma entidade que nós chamamos de banco de dados. Ou, também, dentro do MySQL chama banco de dados de schema.

- A entidade básica onde a informação fica armazenada, onde o dado está armazenado, a gente chama de Tabela.

- Então, um banco de dados pode ter uma ou mais tabelas, e cada tabela tem dados armazenados dentro dela.

- Temos campos, que são as colunas, e registros, que são as linhas.

- Chave primária:Eu especifico uma ou mais colunas da tabela, e se eu disser que essas colunas são chaves primárias da tabela, eu não vou poder ter nenhuma linha dentro da minha tabela cuja chave primária se repita. Se isso acontecer, o banco não vai deixar eu colocar essa informação.

- Chave Estrangeira: É uma ligação que a tabela faz com outra tabela.A chave estrangeira liga campos de duas tabelas diferentes do mesmo tipo, não precisam ter o mesmo nome, mas o tipo, sim. Normalmente, quando a gente cria a chave estrangeira a gente tem uma tabela pai e uma tabela filho.De tal maneira que, na tabela filho, eu só vou poder ter elementos que estão previamente cadastrados na tabela pai.

```
Analogia:
Se eu tenho uma tabela de clientes cuja chave primária é o CPF e tenho uma tabela de vendas onde eu tenho a informação de cada venda que é efetuada na minha empresa, na linha da tabela de vendas eu tenho também o cliente.

Se eu crio uma chave estrangeira entre o cliente da tabela de clientes e o cliente da tabela de vendas, o que acontece? Eu só vou poder vender com clientes que existam na tabela cadastral.
```
- Índice: É como se fosse um cadastro de posições dos elementos dentro da tabela, de tal maneira que quando eu vou buscar um elemento na tabela, se eu tiver um índice eu acho esse elemento mais fácil, porque, ao invés de eu percorrer a tabela toda, linha a linha, eu vou no índice, procuro o elemento, e vai dizer: "olha, esse cara está na posição 25".

- Quando a gente cria uma chave primária e uma chave estrangeira, automaticamente o MySQL já cria um índice para esses dois campos.
E por que? Porque, claro, chave estrangeira, chave primária, vão fazer com que o banco busque toda hora esses elementos nessas tabelas, justamente pra saber se há um relacionamento íntegro.

```
Ok, então meu banco tem várias tabelas, dentro da tabela eu tenho chaves primárias, tenho campos, tenho os registros, e aí as tabelas podem se organizar em esquemas.

No MySQL o esquema e o banco de dados é a mesma coisa, mas essa transparência está mostrando grupos de tabelas diferentes porque em outros bancos de dados relacionais há uma diferenciação entre o esquema e o banco de dados.

```
- View: é uma tabela lógica que é feita através da construção de uma consulta. Toda vez que eu consultar a view, a consulta que está lá vai ser resolvida.
Uma view tem uma performance muito menor do que eu fazer a consulta direto em uma tabela, mas as views são muito importantes quando eu quero disponibilizar parte do meu banco para alguém externo, por exemplo, eu construo uma view, nessa view eu limito aquilo que aquela pessoa externa pode ver, e aí lá no usuário do meu banco de dados eu digo: "olha, esse usuário só consegue enxergar tal view".

- Stored procedure: São programas estruturados, usando a linguagem SQL, que eu posso fazer para operações mais complexas.O SQL é uma linguagem não muito estruturada, ele não tem IFs, ELSEs, eu não consigo fazer programas fazendo desvios.O padrão ANSI é assim, mas cada banco de dados disponibiliza para o seu usuário uma outra linguagem estruturada que utiliza comandos de SQL diretamente, que faz com que eu possa construir coisas rebuscadas.

- Trigger: são regras/ordens que eu vou executar quando algo acontece no banco, são muito importantes, porque, às vezes, ao incluir dados de uma tabela eu tenho que fazer algum tipo de pré cálculo em outra tabela, então o trigger pode fazer isso.