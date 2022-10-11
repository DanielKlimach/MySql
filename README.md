# MySql
# Resumo do MySql

create database MeuBanco; //cria um datbase<br/>
drop database MeuBanco. //exclui um database<br/>
use MeuBanco; //usar uma determinada database<br/>

<hr/>

tipos de dados:<br/>
texto = varchar();<br/>
numero = int();<br/>
datas = date;<br/>

<hr/>

create table minhaTabela(<br/>
&ensp; id int not null primary key auto auto_increment,<br/>
&ensp; nome varchar(50) not null<br/>
&ensp; profissao varchar(50) not null,<br/>
&ensp; idade int not null<br/>
);<br/>

drop table minhaTabela; //exclui a tabela<br/>

alter table minhaTabela add column idade int; //adicionei uma coluna em uma tabela existente<br/>
alter table minhaTabela drop column idade; //removi uma coluna da minha tabela<br/>

<hr/>

C: Create = Insert<br/>
R: Read = Select<br/>
U: Update = <br/>
D: Delete = Drop<br/>

Create:<br/>
insert into minhaTabela (nome, profissao, idade) values <br/>
 &ensp; ("Daniel", "Programador", 21),<br/>
 &ensp; ("Gabriel", "Programador", 19),<br/>
 &ensp; ("Sarah", "Atriz", 20);<br/>

Read:<br/>
select * from minhaTabela;<br/>
select nome from minhaTabela where idade > 20 or profissao = "Atriz";<br/>

Update:<br/>
set SQL_SAFE_UPDATES = 0; //COMANDO PARA HABILITAR UPDATES AVONTADE<br/>
update Tabela set idade = 20 where nome = "GABRIEL";<br/>

Delete:<br/>
delete from minhaTabela where profissao = "Atriz";<br/>

<hr/>
Referencias:<br/>
create table enderecos(<br/>
 &ensp; id int not null primary key auto_increment,<br/>
 &ensp; endereco varchar(50) not null,<br/>
 &ensp; pessoa_id int not null,<br/>
 &ensp; foreign key (pessoa_id) references tabela(id)<br/>
);<br/>

insert into enderecos(endereco, pessoa_id) values<br/>
("QNJ 40 Conj K", 1),<br/>
("QNO 7 Conj N", 2);<br/>

<hr/>

JOIN: Consulta de uma ou mais tabelas por meio de uma relação<br/>

ineer join: Apenas que existam ocorrência com os dois lados<br/>
left join: Recebe todas as informações da primeira tabela e apenas as informações que tenham ocorrência na segunda tabela<br/>
right join: Recebe todas as informações da segunda tabela e apenas as informações que tenham ocorrência na primeira tabela<br/>

select minhaTabela.nome, enderecos.* from tabela <br/>
inner join enderecos on tabela.id = enderecos.pessoa_id;<br/>

<hr/>

Funções Agregadas:<br/>

select sum(idade) as soma_idades from minhaTabela; //somará todas as idades e dará o resultado final. "AS" é para renomear a visualização do nome da coluna<br/>
select count(id) as qtd_pessoas from minhaTabela; //contará quantos ids tem nessa tabela<br/>
select profissao, count(id) as qtd_pessoas from minhaTabela group by profissao; //organiza, agrupando as linhas, no caso a profissao(caso se repita agrupará em uma só linha)<br/>








