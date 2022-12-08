# Resolução da Prova Prática Banco de Dados

## 1ª Questão
Faça um comando SQL para matricular o aluno "Pedro César" no  curso de informática.Os dados devem ser inseridos na tabela TB_MATRÍCULA.

```sql
select * from tb_aluno
insert into tb_aluno(codigo_aluno, nome_aluno, ano_nasc, email, sexo)
values ('4', 'Pedro César', '1995-06-04', 'pedro@provaSQL.com.br', 'M')
select * from tb_matricula
insert into tb_matricula(codigo_curso, codigo_aluno)
values ('4', '4')
```
## Resultado 

![q1 2Db](https://user-images.githubusercontent.com/114403979/206186429-af1a1a67-b402-4d8d-9c29-eb38b7826505.png)
<br/>
![q1DB](https://user-images.githubusercontent.com/114403979/206186442-0047b5c9-f95d-4b70-99e5-2033b8503a11.png)


## 2ª Questão
Escreva um comando SQL que retorne os nomes dos alunos e do(s) cursos em que estão matriculados.Os dados deverão estar ordenados pelo nome do curso.  

```sql
select tb_aluno.nome_aluno, tb_curso.nome_curso
from tb_aluno
inner join tb_matricula
on tb_aluno.codigo_aluno = tb_matricula.codigo_aluno
inner join tb_curso
on tb_curso.codigo_curso = tb_matricula.codigo_curso
```
## Resultado 

![q2DB](https://user-images.githubusercontent.com/114403979/206186499-aa04cc46-34ac-4e64-b51f-1843522f754f.png)


## 3ª Questão
Crie um comando SQL que retorne o e-mail de todos os alunos maiores de idade.

```sql
select email
from tb_aluno where 2022 - ano_nasc >= 18
```
## Resultado 

![q3DB](https://user-images.githubusercontent.com/114403979/206186533-a190cc9f-05e8-4611-a4ea-f29c2c64f3d8.png)


## 4ª Questão
Desenvolva um comando SQL que mostre o total de alunos.

```sql
select count(codigo_aluno)
from tb_aluno
```
## Resultado 

![q4DB](https://user-images.githubusercontent.com/114403979/206186568-aa8d2e99-5bd3-437c-a59c-e5c1cbec1640.png)


## 5ª Questão
Escreva um comando SQL para listar o total de alunos matriculados em cada curso.

```sql
select tb_curso.nome_curso,
codigo_curso + codigo_aluno as numero_alunos
from tb_curso
inner join tb_aluno
on tb_aluno.codigo_aluno = tb_curso.codigo_curso
```
## Resultado 


![q5DB](https://user-images.githubusercontent.com/114403979/206186607-70f17862-97dd-4c9e-8318-ca044ccb31a5.png)

## 6ª Questão
Desenvolva um comando SQL que retorne o nome de todos os alunos maiores que 18 anos.

```sql
select nome_aluno
from tb_aluno where 2022 - ano_nasc >= 18
```
## Resultado 

![02](https://user-images.githubusercontent.com/105735037/206178292-be49f604-890b-494c-9a4b-07f093e433c1.PNG)

## 7ª Questão
Faça um comando SQL que retorne o nome de todas as mulheres. 

```sql
select nome_aluno, sexo
from tb_aluno where sexo = 'F'
```
## Resultado 

![q7DB](https://user-images.githubusercontent.com/114403979/206186706-6570fca1-5caa-41d0-8a2f-c71fc50761dd.png)


## 8ª Questão
Faça um comando SQL que retorne o nome de todas as mulheres matriculadas no curso de Medicina.

```sql
select tb_aluno.nome_aluno as mulheres_em_medicina
from tb_aluno
inner join tb_matricula
on tb_matricula.codigo_aluno = tb_aluno.codigo_aluno
and tb_matricula.codigo_curso = 1
and tb_aluno.sexo = 'F'
```
## Resultado 

![q8DB](https://user-images.githubusercontent.com/114403979/206186751-fd47532f-a7c7-4ba0-ac4a-5aa069914f5b.png)


## 9ª Questão
Faça um comando SQL que retorne os nomes dos cursos ordenados por ordem alfabética.

```sql
select nome_curso
from tb_curo order by nome_curso asc
```
## Resultado 

![q9DB](https://user-images.githubusercontent.com/114403979/206186768-c63918de-50f1-41da-a721-61b891b4f73e.png)

## 10ª Questão
Crie o enunciado de uma consulta SQL que utiliza "junção" (com resposta).

```sql
select ano_nasc,tb_curso.nome_curso,tb_aluno.nome_aluno
from tb_aluno
inner join tb_curso
on tb_aluno.cod_aluno = tb_curso.cod_curso
order by nome_curso asc 
```
## Resultado 
![trabadoDD](https://user-images.githubusercontent.com/104003510/206247087-8d9edbac-8794-418b-b4c2-034bb61a5c69.jpg)

# Resolução da Prova Teórica

Questão 1:
SQL é o acrônimo para Structured Query Language.É uma linguagem pra acesso e manipulação de dados,principalmente para banco de dados relacionais.

Questão 2:
A linguagem SQL foi originalmente desenvolvida no laboratório de pesquisa da IBM em San José, em conexão com um projeto de desenvolvimento de um protótipo para um sistema de gerenciamento de banco de dados relacional chamado System R no início dos anos 70.
Os primeiros sistemas de gerenciamento de banco de dados baseados em SQL tornaram-se disponíveis comercialmente no final dos anos 70. Ao mesmo tempo, foram publicados sistemas de gerenciamento de banco de dados relacional baseados em outras linguagens. A alternativa mais conhecida para SQL era a linguagem QUEL no sistema Ingres.
SQL foi eleito para padronização. Tanto a ANSI americana quanto a ISO internacional participaram da padronização
Em 1986, o primeiro padrão SQL foi aprovado (o núcleo SQL cerca de 40 páginas + a linguagem do módulo e a incorporação em linguagens de programação, ao todo cerca de 100 páginas)
Em 1989, um aprimoramento de integridade foi aprovado pela ISO, contendo, entre outros recursos, a possibilidade de especificação de chaves, chaves estrangeiras e algumas outras restrições (c. 20 páginas)
Em 1992, foi aprovada a nova versão SQL-92 (também chamada de SQL2). Ele continha grandes melhorias para o idioma. O tamanho do padrão era de cerca. 600 páginas + o padrão do dicionário de dados. 

Questão 3:
SQL é uma linguagem padrão para trabalhar com bancos de dados relacionais. Ela é uma linguagem declarativa e que não necessita de profundos conhecimentos de programação para que alguém possa começar a escrever queries. A linguagem SQL é utilizada de maneira relativamente parecida entre os principais bancos de dados relacionais do mercado: Oracle, MySQL, MariaDB, PostgreSQL, Microsoft SQL Server, entre muitos outros. Cada um tem suas características, sendo o MySQL e o PostgreSQL extremamente populares por possuírem versões gratuitas e de código aberto.

Questão 4:
O comando SELECT é utilizado para extrair os dados das tabelas de um banco de dados. Ele pode extrair dados de uma ou mais tabelas ao mesmo tempo, executando desde simples consultas até comandos mais complexos, fazendo buscas, junções, filtros comparativos, ordenações e diversos outros itens.

Questão 5:
O SQL Server, criado pela Microsoft, é muito conhecido e utilizado no mercado. A linguagem usada nessa ferramenta é o T-SQL, e oferece recursos avançados e diferenciados para facilitar a atualização de dados e o armazenamento das informações de forma segura e confiável. O SQL Server atua com sistemas integrados de criptografia, permitindo que a visualização ou alteração das informações sejam feitas apenas pelas pessoas responsáveis, o que garante ainda mais segurança e tranquilidade para os usuários e empresários. É uma alternativa comumente utilizada em lojas online, instituições governamentais, bancos e indústrias dos mais diversos portes.

