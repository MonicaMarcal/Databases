Todos os bancos de dados relacionais - seja ele MySQL, Oracle ou SQL Server, da Microsoft - eles possuem tipos de campos muito parecidos, mas os nomes e as referências desses campos podem mudar de um campo para outro, e aí antes da modelagem, antes de você projetar o seu banco, é legal que você saiba que tipos de dados você tem à disposição para saber como você vai usar na sua modelagem.

<br>

### INTEIROS:
Número inteiros são número que não têm casas decimais, e aí nós temos, em uma SQL, cinco tipos de número inteiros.
- Tinyint, Smallint, Mediumint, Int e Bigint.

A diferença desses campos é o número de bytes que cada um armazena dentro do banco.
Saber os tipos de campos e o tamanho que eles vão armazenar, para você projetar bancos de dados mais otimizados.

- O Tinynt vai de -128 a +127; 
- o Smallint vai de -32.768 a 32.767, só que quando a gente cria um campo numérico a gente tem uma propriedade no MySQL chamado Unsigned.

 O unsigned significa o seguinte: se eu digo que um campo é unsigned, ele não vai ter negativo, ele só vai ter número positivo, e aí o menos do número negativo é uma coisa que ocupa espaço no armazenamento do campo, então, quando eu digo que o número não tem número negativo, o range, ou seja, o espaço que eu tenho armazenado para gravar números positivos aumenta.

- Então, quando o número é unsigned, o tinyint, que o limite máximo seria 127 passa a ser 255.
- O smallint, que o valor mínimo era 32.767, passa a ser 65.535.

Então há um aumento desse valor do espaço reservado para armazenagem do número inteiro, e isso se aplica ao mediumint, ao int e ao bigint.

<br>

### DECIMAIS:
- Temos o Float e o Double.

A diferença deles é a precisão: uma usa a precisão simples e a outra usa a precisão dupla.Uma ocupa 4 bytes do meu banco e o outro ocupa 8 bytes.


O precisão tem muito a ver com a forma com que o número é armazenado, então, às vezes o número, internamente, ele é armazenado com muitas casas decimais, mas a gente, depois, quando visualiza ele, ele faz uma aproximação através desse ponto flutuante no valor decimal que ele realmente tem.

- Se eu digo que um campo, por exemplo, é float de 7 dígitos com 4 casas decimais, ou seja, o primeiro parâmetro do float é o número de dígitos totais do número incluindo os decimais, e o que eu tenho depois da vírgula é só o que eu vou ter na parte decimal.

- Se eu digo que o float é 7 de 4, um número, por exemplo, 999,00009, quando eu armazenar, ele será armazenado como 999,0001, ou seja, ele vai arredondar esse número e armazenar dentro do espaço que foi determinado.

Outros números decimais mas que não são de pontos flutuantes é o Decimal ou Numeric, pode ser um ou outro, eles são iguais.

Eles armazenam número de até 65 dígitos, incluindo as casas decimais, e esses números são fixos, esse tamanho é fixo, ou seja, quando eu coloco o número lá ele vai ocupar o número de casas decimais até o finalzinho do que o número ocupa.

O tipo Bit, como o próprio nome diz, é um bit apenas.
Mas eu posso ter um campo de bit de 2, de 3, de 4, mas o conteúdo lá dentro vai ser caracteres binários: ou 1 ou 0. Então, se eu digo que é bit de 1, eu posso armazenar ou 1 ou 0, mas se eu digo que o campo é bit de 2 eu posso armazenar 01, 10, 00 ou 11, ou seja, eu tenho 4 tipos de números binários que eu posso armazenar no bit de 2.
- Normalmente o bit 1 a gente utiliza para armazenar campos lógicos onde eu tenho alguma coisa que é verdadeira ou falsa, e normalmente a gente aplica o 1 para o verdadeiro e o 0 para o falso.

- Os campos numéricos possuem atributos, signed ou unsigned, se o número vai ter ou não número negativo.

Zerofil, alguns números, geralmente os que não são de ponto flutuante, eu preencho com zeros os espaços antes do número inteiro até chegar ao tamanho do número.

- Um número inteiro que eu armazeno, o número 5, eu vou armazenar o número 0005, ou seja, eu vou colocar 3 zeros na frente de tal maneira que o número de dígitos bata com esse número que eu acrescentei aqui.

A gente tem também campos numéricos que são do tipo auto incremento.

- O auto incremento é um número sequencial que vai ser crescido automaticamente na medida em que eu vou inserindo dados da tabela, e aí além de crescimento desse número sequencial eu posso determinar, pode ser um número que cresça de 1 em 1, de 5 em 5, e assim por diante.
- O auto incremento ele é muito usado quando eu quero criar chaves primárias randômicas, que não vão se repetir nunca.Randômicas, não, sequenciais.

Quando a gente tenta armazenar um número maior do que ele suporta, eu digo que o número é um tinyint ou smallint e eu quero gravar um número grande, eu sempre vou ter erro no momento da gravação, que são os erros chamados de out of range.

 - erro do tipo out of range, é alguma coisa que você que gravar que é maior do que é suportado.

A gente tem os campos de data, que são superimportantes no banco de dados, e aí eu posso ter tipos de bancos diferentes.

- Date é um campo de data que somente vai armazenar ano, mês e dia, e varia do dia 1 de janeiro do ano 1000 até o último dia de dezembro de 9.999.

- Date time é igual ao date, só que além da data, eu armazeno a hora, então eu posso, também, ter uma precisão maior do dado armazenado, e aqui em cima vocês podem ver o limite inferior e superior.

- Timestamp é parecidíssimo com o date time, só que ele tem um limite menor e ele utiliza o fuso horário para estar armazenando a informação.
- Normalmente, a informação vem com o fuso horário de Greenwich, que é o fuso horário padrão do mundo.

Os campos string nós chamamos de dois: varchar e char.

- O char tem valor fixo, ou seja, quando a gente diz que o char tem 255 caracteres, se eu gravar um caracter com 1 dígito apenas, por exemplo a letra A, ele vai ocupar os 255 dígitos. Ele vai gravar o A e 254 espaços em branco.

- O varchar, apesar de eu dizer que há um limite máximo de tamanho, se eu gravo a letra A nesse exemplo e o campo tem 255 dígitos, eu só gravo 1 dígito na base. O varchar ele é mais inteligente para controlar tamanhos.

Eu tenho também os valores binários, que também podem variar de 0 a 255 caracteres, porém os dados que são gravados são bits, 1, 0, 0, 1 e assim por diante.Não consigo ver, ali, letras nem números, só o número 1 e o número 0.

Temos alguns strings que nós chamamos de strings longos.
Tem alguns tipos: tinyblob, blob, mediumblob, longblob.E o texto, que é o texto longo.

- O blob eu uso para gravar coisas binárias, então, por exemplo, eu posso gravar o conteúdo de uma foto, de um arquivo, que é binário, no campo blob.
- Já no campo texto é só caracteres que respeitam as tabelas ASCIIS dependendo de cada tabela que o computador suporta, que são tabelas que convertem números em letras.

O enum são campos que me dão opções, então, por exemplo, eu digo que o campo é do tipo enum e tenho aqui: x-small, small, medium, large, x-large.
Ou seja, quando eu dou insert nesse campo, se eu der um string diferente desse conjunto que está aqui, o banco de dados vai me dar um erro, vai dizer que eu não posso.
Esses são os campos do tipo enum.

Todos os campos string têm um campo chamado set e collate, que têm a ver com o conjunto de caracteres suportados, com aquelas tabelas ASCIIs. Há um conjunto de tabelas que suporta outros símbolos além dos que você vê no seu teclado.(geometric, mapa, point,  line string, polígono)


