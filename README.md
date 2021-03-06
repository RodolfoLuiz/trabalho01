# TRABALHO 01:  ANTI-FIRE COMPANY
Trabalho desenvolvido durante a disciplina de Banco de Dados do Integrado

# Sumário

### 1. COMPONENTES<br>
Integrantes do grupo<br>
Rodolfo Luiz de Oliveira: rodolfoliveira99@gmail.com<br>
Gustavo Olmo Santana: gustavo.olmosantana@gmail.com<br>


### 2.INTRODUÇÃO E MOTIVAÇAO<br>
Este documento contém a especificação do projeto do banco de dados <> 
<br>e motivação da escolha realizada. <br>

  A empresa "Anti-Fire Company" está disposta a colaborar com projetos, para uma sociedade mais segura. O sistema (ainda em projeto) tem como função, detectar através de sensores, materiais inflamáveis ao nosso redor, e com isso, evitar incêndios  em muitas áreas. 
A inspiração foi dada pelos recentes acontecimentos registrados de vários incendios que levam cinzas para diversas áreas do mundo. 
Acreditamos que essa ideia seja uma maneira de inovar a segurança das pessoas ao redor do país.
 

### 3.MINI-MUNDO <br>

>  O projeto armazenará detalhadamente todos os tipos de incidentes (ex.: incendios, vazamentos de gás, etc) e suas respectivas informações (ex.: hórario, data, temperatura, umidade ). Serão cuidadosamente detectadas através de sensores (de temperatura, umidade, gases dispersos no ambiente) que quando registrar alguma situação crítica ou desfavorável, automaticamente acionará o sistema e comunicará os bombeiros, além de armazenar no sistema as informações do incidente, anteriormente citados. No site do projeto, você (cliente) poderá se cadastrar inserindo algumas informações pessoais(ex.: nome, cpf, rg, telefone, e-mail, data de nascimento), informações sobre seu imóvel, como a quantidade de cômodos e sua funcionalidade (residencial ou comercial) e seu endereço (para solicitar intalação e posteriormente uma manutenção), após a instalação tambem será armazenada a data de instalação.


### 4.RASCUNHOS BÁSICOS DA INTERFACE (MOCKUPS)<br>

![Alt text](https://github.com/RodolfoLuiz/trabalho01/blob/master/print%20balsamiq.png "Title")
![Arquivo PDF do Protótipo Balsamiq feito para Empresa Anti-Fire Company ](https://github.com/RodolfoLuiz/trabalho01/blob/master/MOD.pdf)


#### 4.1 QUAIS PERGUNTAS PODEM SER RESPONDIDAS COM O SISTEMA PROPOSTO? 

> A Empresa Anti-Fire Company precisa inicialmente dos seguintes relatórios:
+ Relatório mostrando qual é o tipo de imóvel que mais ocorrem incidentes;
+ Relatório de Incidentes mais comuns nos imóveis;
+ Relatório da quantidade de lucro em cada estado; (qual região retorna o maior lucro para os supervisores?)
+ Relatório sobre a quantidade de imóveis em cada região do país;
+ Relatório dos estados onde o sistema é vendido em maior quantidade.


#### 4.2 TABELA DE DADOS DO SISTEMA:
![Tabela de dados da Empresa Anti-Fire Company ](https://github.com/RodolfoLuiz/trabalho01/blob/master/Tabela%20BRABA%20FINALizada.ods)

    
### 5.MODELO CONCEITUAL<br>
    A) NOTACAO ENTIDADE RELACIONAMENTO 
        * Para nosso prótótipo limitaremos o modelo conceitual nas 5 principais entidades do escopo
        * O protótipo deve possui no mínimo duas relações N para N
        
![Alt text](https://github.com/RodolfoLuiz/trabalho01/blob/master/MODELO%20CONCEITUAL%202710.png)
    
    B) QUALIDADE 
        Garantir que a semântica dos atributos seja clara no esquema
        Criar o esquema de forma a garantir a redução de informação redundante, possibilidade de valores null, 
        e tuplas falsas
    
        
#### 5.1 Validação do Modelo Conceitual
    [Grupo01]: [Calebe Carias e Davi Moura]
    [Grupo02]: [Júlia Suzano]
    
    
#### 5.2 DESCRIÇÃO DOS DADOS

CLIENTE: Tabela que armazena as informações referentes aos clientes.<br>
NOME: Campo que armazena o nome de cada cliente da empresa.<br>
RG: Campo que armazena o Registro Geral dos clientes.<br>
CPF: Campo que armazena o número de Cadastro de Pessoa Física de cada cliente da empresa.<br>
DATA_NASC: Campo que armazena a data de nascimento dos clientes.<br>

IMOVEL: Tabela que armazena as informações referentes aos imóveis cadastrados pelos clientes.<br>
NUMERO: Campo que diz o número do imóvel do cliente. <br>
CODIGO: Campo que armazena o código identificador de cada imóvel cadastrado. <br>
TIPO: Campo que armazena o tipo do imóvel cadastrado. Por exemplo: Comercial, Residencial, Industrial. <br>
NUM_COMODOS: Campo que armazena o número de cômodos existentes em cada imóvel.<br>
DATA_MANUTENCAO: Campo que armazena a data da última manutenção realizada no imóvel. <br>

REGISTRO: Tabela que armazena informações, fornecidas pelos sensores, referentes aos incidentes ocorridos em cada um dos imóveis cadastrados.<br>
DATA: Campo que armazena a data dos incidentes.<br>
TEMPERATURA: Campo que armazena a temperatura máxima registrada pelos sensores durante o incidente.<br>
HORA:  Campo que armazena o horário em que os sensores foram acionados, e detectaram o incidente.<br>
UMIDADE: Campo que armazena a umidade registrada pelos sensores durante o incidente.<br>
ID: Campo que armazena o identificador dos sensores.<br>

CATEGORIA: Informações detalhadas sobre incidentes ocorridos. <br>
TIPO: Causa primária do incidente. <br>
CODIGO: Campo identificador dos sensores. <br>

ESTADO: Espaço onde é mostrado o Estado onde o imóvel está localizado.<br>
BAIRRO: Espaço onde é mostrado o Bairro onde o imóvel está localizado.<br>

SUPERVISOR: Tabela que representam os Supervisores de cada imóvel, dividos em estados. <br>
SALARIO: respectivo de cada supervisor diferente. <br>

CONTATO: maneira de entrar em contato com clientes. <br>
TIPO: espécie do contato (rede social, telefone, e-mail, etc).<br>
 
### 6	MODELO LÓGICO<br>
  ![Alt text](https://github.com/RodolfoLuiz/trabalho01/blob/master/MODELO%20L%C3%93GICO%202710.png)

### 7	MODELO FÍSICO<br>

CREATE TABLE CLIENTE ( Nome varchar(50), CPF varchar(50), Data_nasc date, RG varchar(50) PRIMARY KEY);

CREATE TABLE REGISTRO ( Data date, Temperatura int, Hora time, Umidade float, ID varchar(50) PRIMARY KEY, FK_IMOVEL_Codigo varchar(50), FK_CATEGORIA_Codigo int);

CREATE TABLE IMOVEL ( Num_Comodos int, Data_Manutencao date, Codigo varchar(50) PRIMARY KEY, CEP varchar(50), Numero varchar(50), FK_CLIENTE_RG varchar(50), FK_SUPERVISOR_Codigo int, FK_ESTADO_ID int, FK_BAIRRO_ID int, FK_CLASSE_ID int);

CREATE TABLE SUPERVISOR ( Salario float, RG varchar(50), Codigo int PRIMARY KEY, Nome varchar(50), FK_ESTADO_ID int);

CREATE TABLE CATEGORIA ( Codigo int PRIMARY KEY, Tipo varchar(50));

CREATE TABLE ESTADO ( ID int PRIMARY KEY, Nome varchar(50));

CREATE TABLE BAIRRO ( ID int PRIMARY KEY, Nome varchar(50));

CREATE TABLE CONTATO ( Codigo int PRIMARY KEY, Contato varchar(50), FK_CLIENTE_RG varchar(50), FK_TIPO_ID int);

CREATE TABLE TIPO ( ID int PRIMARY KEY, Tipo varchar(50));

CREATE TABLE CLASSE ( ID int PRIMARY KEY, Tipo varchar(50));

CREATE TABLE Cliente_Supervisor ( fk_CLIENTE_RG varchar(50), fk_SUPERVISOR_Codigo int );

ALTER TABLE REGISTRO ADD CONSTRAINT FK_REGISTRO_2 FOREIGN KEY (FK_IMOVEL_Codigo) REFERENCES IMOVEL (Codigo) ON DELETE CASCADE;

ALTER TABLE REGISTRO ADD CONSTRAINT FK_REGISTRO_3 FOREIGN KEY (FK_CATEGORIA_Codigo) REFERENCES CATEGORIA (Codigo) ON DELETE CASCADE;

ALTER TABLE IMOVEL ADD CONSTRAINT FK_IMOVEL_2 FOREIGN KEY (FK_CLIENTE_RG) REFERENCES CLIENTE (RG) ON DELETE RESTRICT;

ALTER TABLE IMOVEL ADD CONSTRAINT FK_IMOVEL_3 FOREIGN KEY (FK_SUPERVISOR_Codigo) REFERENCES SUPERVISOR (Codigo) ON DELETE RESTRICT;

ALTER TABLE IMOVEL ADD CONSTRAINT FK_IMOVEL_4 FOREIGN KEY (FK_ESTADO_ID) REFERENCES ESTADO (ID) ON DELETE CASCADE;

ALTER TABLE IMOVEL ADD CONSTRAINT FK_IMOVEL_5 FOREIGN KEY (FK_BAIRRO_ID) REFERENCES BAIRRO (ID) ON DELETE CASCADE;

ALTER TABLE IMOVEL ADD CONSTRAINT FK_IMOVEL_6 FOREIGN KEY (FK_CLASSE_ID) REFERENCES CLASSE (ID) ON DELETE CASCADE;

ALTER TABLE SUPERVISOR ADD CONSTRAINT FK_SUPERVISOR_2 FOREIGN KEY (FK_ESTADO_ID) REFERENCES ESTADO (ID) ON DELETE CASCADE;

ALTER TABLE CONTATO ADD CONSTRAINT FK_CONTATO_2 FOREIGN KEY (FK_CLIENTE_RG) REFERENCES CLIENTE (RG) ON DELETE RESTRICT;

ALTER TABLE CONTATO ADD CONSTRAINT FK_CONTATO_3 FOREIGN KEY (FK_TIPO_ID) REFERENCES TIPO (ID) ON DELETE CASCADE;

ALTER TABLE Cliente_Supervisor ADD CONSTRAINT FK_Cliente_Supervisor_1 FOREIGN KEY (fk_CLIENTE_RG) REFERENCES CLIENTE (RG) ON DELETE RESTRICT;

ALTER TABLE Cliente_Supervisor ADD CONSTRAINT FK_Cliente_Supervisor_2 FOREIGN KEY (fk_SUPERVISOR_Codigo) REFERENCES SUPERVISOR (Codigo) ON DELETE RESTRICT;

ALTER TABLE Cliente_Supervisor ADD CONSTRAINT PK_Cliente_Supervisor PRIMARY KEY (fk_CLIENTE_RG,fk_SUPERVISOR_Codigo);


### 8	INSERT APLICADO NAS TABELAS DO BANCO DE DADOS<br>

#TABELA CLIENTE - FINAL

cur.execute("start transaction")
fake = Factory.create('pt_BR')

for i in range(50):
  i = i + 1
  nome = fake.name()
  Data_nasc = fake.date(pattern="%Y-%m-%d", end_datetime=None)
  RG = fake.rg()
  CPF = fake.cpf()
  
  insert_values = (nome,CPF,Data_nasc,RG)
  insert_instruction = """insert into CLIENTE values (%s,%s,%s,%s)"""
  cur.execute(insert_instruction, insert_values)
  cur.execute("commit")
  
-------------------------------------------------------------------------------------------------------------

#TABELA SUPERVISOR - FINAL

cur.execute("start transaction")
fake = Factory.create('pt_BR')

for i in range(50):
  nome = fake.name()
  RG = fake.rg()
  salario = fake.pyint(min_value=1000, max_value=20000, step=10)
  codigo = i + 1
  
  FK_ESTADO_ID = random.randint(2,51)
  
  insert_values = (salario,RG,codigo,nome,FK_ESTADO_ID)
  insert_instruction = """insert into SUPERVISOR values (%s,%s,%s,%s,%s)"""
  cur.execute(insert_instruction, insert_values)
  cur.execute("commit")
  
--------------------------------------------------------------------------------------------------------------

#TABELA IMÓVEL COMPLETA

cur.execute("start transaction")
fake = Factory.create('pt_BR')

for i in range(50):
  numero = fake.building_number()
  num_comodos = fake.pyint(min_value=1, max_value=10, step=1)
  Data_manutencao = fake.date(pattern="%Y-%m-%d", end_datetime=None)
  codigo = i + 1
  CEP = fake.ssn()

  sorteio = random.randint(1,50)
  FK_CLIENTE_RG = Cliente_Supervisor[sorteio][0]
  FK_SUPERVISOR_Codigo = Cliente_Supervisor[sorteio][1]
  FK_ESTADO_ID = random.randint(2,51)
  FK_BAIRRO_ID = random.randint(2,51)
  FK_CLASSE_ID = random.randint(1,3)
  
  insert_values =(num_comodos,Data_manutencao,codigo,CEP,numero,FK_CLIENTE_RG,FK_SUPERVISOR_Codigo,FK_ESTADO_ID,FK_BAIRRO_ID,
  FK_CLASSE_ID)
  insert_instruction = """insert into IMOVEL values (%s,%s,%s,%s,%s,%s,%s,%s,%s,%s)"""
  cur.execute(insert_instruction, insert_values)
  cur.execute("commit")
  
--------------------------------------------------------------------------------------------------------------

#TABELA ESTADO - FINALIZADA

cur.execute("start transaction")
fake = Factory.create('pt_BR')

for i in range(50):
  codigo = i + 2
  i = i + 1
  
  nome = fake.estado_nome()	
  
  insert_values = (codigo, nome)
  insert_instruction = """insert into ESTADO values (%s,%s)"""
  cur.execute(insert_instruction, insert_values)
  cur.execute("commit")

--------------------------------------------------------------------------------------------------------------

#TABELA BAIRRO - FINALIZADA

cur.execute("start transaction")
fake = Factory.create('pt_BR')

for i in range(50):
  i = i + 1
  codigo = i + 1
  nome = fake.bairro()
  
  insert_values = (codigo, nome)
  insert_instruction = """insert into BAIRRO values (%s,%s)"""
  cur.execute(insert_instruction, insert_values)
  cur.execute("commit")

--------------------------------------------------------------------------------------------------------------
  
#TABELA CLASSE - FINALIZADA
cur.execute("start transaction")
fake = Factory.create('pt_BR')

t = ["Industrial","Comercial","Residencial"]
for i in range(len(t)): 
  ID = i + 1
  tipo = t[i]
  
  insert_values = (ID,tipo)
  insert_instruction = """insert into CLASSE values (%s,%s)"""
  cur.execute(insert_instruction, insert_values)
  cur.execute("commit")
  
--------------------------------------------------------------------------------------------------------------
  
#TABELA CONTATO - FINAL

cur.execute("start transaction")
fake = Factory.create('pt_BR')

select_instruction_Cliente = """select * from Cliente limit 30"""

cur.execute(select_instruction_Cliente)
clientes = cur.fetchall()

t = ["twitter","telefone","instagram","e-mail","whatsapp"]
for i in range(50):
  codigo = i + 2
  
  randomizar = random.randint(1,5)
  contat = t[randomizar-1]

  FK_CLIENTE_RG = clientes[random.randint(0,29)][3]
  FK_TIPO_ID = random.randint(1,5)
  
  insert_values = (codigo,contat,FK_CLIENTE_RG,FK_TIPO_ID)
  insert_instruction = """insert into CONTATO values (%s,%s,%s,%s)"""
  cur.execute(insert_instruction, insert_values)
  cur.execute("commit")
  
--------------------------------------------------------------------------------------------------------------
  
#TABELA REGISTRO - FINAL

cur.execute("start transaction")
fake = Factory.create('pt_BR')

for i in range(50):
  i = i + 1
  data = fake.date(pattern="%Y-%m-%d", end_datetime=None)
  temperatura= fake.pyint(min_value=35, max_value=100, step=1)
  hora = fake.time(pattern="%H:%M:%S", end_datetime=None) 
  umidade = fake.pyint(min_value=10, max_value=100, step=1)
  ID = i + 1

  FK_IMOVEL_Codigo = random.randint(1,50)
  FK_CATEGORIA_Codigo = random.randint(1,10)

  insert_values = (data,temperatura,hora,umidade,ID,FK_IMOVEL_Codigo,FK_CATEGORIA_Codigo)
  insert_instruction = """insert into REGISTRO values (%s,%s,%s,%s,%s,%s,%s)"""
  cur.execute(insert_instruction, insert_values)
  cur.execute("commit")
  
--------------------------------------------------------------------------------------------------------------
  
#TABELA TIPO - FINALIZADA

cur.execute("start transaction")
fake = Factory.create('pt_BR')

t = ["Twitter","Telefone","Instagram","E-mail","Whatsapp"]
for i in range(len(t)):
  ID = i + 1
  tipo = t[i]
  
  insert_values = (ID,tipo)
  insert_instruction = """insert into TIPO values (%s,%s)"""
  cur.execute(insert_instruction, insert_values)
  cur.execute("commit")
  
--------------------------------------------------------------------------------------------------------------
  
#TABELA CATEGORIA - FINAL

cur.execute("start transaction")
fake = Factory.create('pt_BR')

t = ["Vazamento de gás","Vasilhames de Líquidos Inflamáveis Abertos","Chama exposta","Curto circuito","Fusíveis e dijuntores", "Centelha ou Faísca", "Superaquecimento", "Combustão Espontanea","Fenômenos naturais e atmosféricos", "Convergência Luminosa"]
for i in range(len(t)):
  cod = i + 1
  tipo= t[i]
  
  insert_values = (cod,tipo)
  insert_instruction = """insert into CATEGORIA values (%s,%s)"""
  cur.execute(insert_instruction, insert_values)
  cur.execute("commit")
  
--------------------------------------------------------------------------------------------------------------

#TABELA CLIENTE_SUPERVISOR

cur.execute("start transaction")
fake = Factory.create('pt_BR')

select_instruction_Cliente = """select rg,nome from Cliente"""
select_instruction_Supervisor = """select codigo,nome from Supervisor"""
cur.execute(select_instruction_Cliente)
clientes = cur.fetchall()
cur.execute(select_instruction_Supervisor)
supervisores = cur.fetchall()

for i in range(30):
  print('Cliente:',clientes[random.randint(1,50)][3])
  print('Supervisor:',supervisores[random.randint(1,50)][2])
  fk_CLIENTE_RG = clientes[random.randint(0,29)][3]
  fk_SUPERVISOR_Codigo = supervisores[random.randint(0,29)][2]
  insert_values = (fk_CLIENTE_RG,fk_SUPERVISOR_Codigo)
  insert_instruction = """insert into cliente_supervisor (fk_CLIENTE_RG,fk_SUPERVISOR_Codigo) values (%s,%s)"""
  cur.execute(insert_instruction, insert_values)
  cur.execute("commit")
  
--------------------------------------------------------------------------------------------------------------

### 9	TABELAS E PRINCIPAIS CONSULTAS<br>
    OBS: Incluir para cada tópico as instruções SQL + print mostrando os resultados.<br>
#### 9.1	CONSULTAS DAS TABELAS COM TODOS OS DADOS INSERIDOS (Todas) <br>

![Alt text](https://github.com/RodolfoLuiz/trabalho01/blob/master/PRINT%20TABELA%20CLIENTE.png)    
![Alt text](https://github.com/RodolfoLuiz/trabalho01/blob/master/PRINT%20TABELA%20SUPERVISOR.png)   
![Alt text](https://github.com/RodolfoLuiz/trabalho01/blob/master/PRINT%20TABELA%20ESTADO.png)  
![Alt text](https://github.com/RodolfoLuiz/trabalho01/blob/master/PRINT%20TABELA%20BAIRRO.png)
![Alt text](https://github.com/RodolfoLuiz/trabalho01/blob/master/PRINT%20TABELA%20IMOVEL.png)
![Alt text](https://github.com/RodolfoLuiz/trabalho01/blob/master/PRINT%20TABELA%20CONTATO.png)
![Alt text](https://github.com/RodolfoLuiz/trabalho01/blob/master/PRINT%20TABELA%20REGISTRO.png)
![Alt text](https://github.com/RodolfoLuiz/trabalho01/blob/master/PRINT%20TABELA%20TIPO.png)
![Alt text](https://github.com/RodolfoLuiz/trabalho01/blob/master/PRINT%20TABELA%20CATEGORIA.png)
![Alt text](https://github.com/RodolfoLuiz/trabalho01/blob/master/PRINT%20TABELA%20CLASSE.png)
![Alt text](https://github.com/RodolfoLuiz/trabalho01/blob/master/PRINT%20TABELA%20CLIENTE_SUPERVISOR.png)


#### 9.2	CONSULTAS DAS TABELAS COM FILTROS WHERE (Mínimo 4)<br>
	
	-Select * from Imovel where fk_cliente_rg = '841320767'
	-Select * from Cliente where nome = ‘João Guilherme Nunes’
	-Select * from Imovel where numero = '3'
	-Select * from Registro where temperatura = ‘40’

#### 9.3	CONSULTAS QUE USAM OPERADORES LÓGICOS, ARITMÉTICOS E TABELAS OU CAMPOS RENOMEADOS (Mínimo 11)
    a) Criar 5 consultas que envolvam os operadores lógicos AND, OR e Not:
    	- Select * from Supervisor where salario > 5000 AND salario < 8000
    	- Select * from Imovel where num_comodos >= 3 AND num_comodos <= 5
    	- Select * from cliente where Data_nasc > '1990-01-01' OR cpf = '974.283.015-05'
   	- Select * from contato where codigo >= 20 AND codigo <= 30 
    	- Select nome,rg,cpf from Cliente where rg ilike '7%' OR cpf ilike '5%' 
    b) Criar no mínimo 3 consultas com operadores aritméticos:
    	- Select nome,rg,salario+1500 as salario_decimo_terceiro from supervisor
    	- Select nome,rg,salario-1000 as salario_reduzido_diminuir_gastos from supervisor
	- Select nome, rg, salario*12 as salario_anual_supervisores from supervisor
    c) Criar no mínimo 3 consultas com operação de renomear nomes de campos ou tabelas:
    	- Select codigo, contato as como_entrar_em_contato from contato 
    	- Select rg,cpf,nome as nome_do_cliente from cliente
    	- Select id,hora as hora_registrada, data as data_registrada from registro
	
#### 9.4	CONSULTAS QUE USAM OPERADORES LIKE E DATAS (Mínimo 12) <br>
    a) Criar outras 5 consultas que envolvam like ou ilike:
    - Select nome from Cliente where nome ilike 'A%'
    - Select * from bairro where nome ilike 'Vila%'
    - Select * from estado where nome ilike 'P%' order by nome ASC
    - Select * from contato where fk_cliente_rg ilike '5%'
    - Select * from contato where contato ilike 'W%'
    - Select nome from Cliente where nome ilike '%B%'
    - Select nome from Cliente where nome ilike '%S'
    - Select * from contato where contato ilike 't%'
    - Select * from contato where contato ilike 'w%'
    
    b) Criar uma consulta para cada tipo de função data apresentada:
    - Select * from cliente where data_nasc = '1980-06-04'
    - Select * from registro where data = '2002-07-26'
    - Select * from registro where data = '2002-07-26'

#### 9.5	ATUALIZAÇÃO E EXCLUSÃO DE DADOS (Mínimo 6)<br>
	update Cliente set nome = 'Gustavo Olmo' where nome = 'Dra. Rafaela Duarte';

	update Imovel set num_comodos = '5' where codigo = '9';

	update Imovel set data_manutencao = '1999-07-30	' where data_manutencao = '1971-03-07';

	update contato set contato = '997755312' where codigo_contato = 10;

	delete from Cliente where rg = '123456789';
	
	delete from imovel where  codigo = '101';

#### 9.6	CONSULTAS COM JUNÇÃO E ORDENAÇÃO (Mínimo 6)<br>
        a) Uma junção que envolva todas as tabelas possuindo no mínimo 3 registros no resultado
	-
	
	
        b) Outras junções que o grupo considere como sendo as de principal importância para o trabalho
	- Select tipo,numero,codigo from classe inner join imovel on (classe.id = imovel.fk_classe_id )  order by classe ASC
	- Select numero,estado from imovel inner join estado on (estado.id = imovel.fk_estado_id ) 
	- Select numero,bairro from imovel inner join bairro on (bairro.id = imovel.fk_bairro_id )
	- Select numero,cep,tipo from imovel inner join classe on (classe.id = imovel.fk_classe_id) 
	- Select numero,cep,tipo from imovel inner join categoria on (categoria.codigo = imovel.fk_classe_id)
        
#### 9.7	CONSULTAS COM GROUP BY E FUNÇÕES DE AGRUPAMENTO (Mínimo 6)<br>
	- Select max(salario) as maior_salario from supervisor
	- Select numero ,count(*) from imovel group by numero
	- Select AVG(salario) as media_dos_salarios from supervisor
	- Select tipo,count(*) from classe inner join imovel on (classe.id = imovel.fk_classe_id ) group by tipo
	- Select AVG(num_comodos) as media_comodos from Imovel
	- Select min(salario) as menor_salario from supervisor

#### 9.8	CONSULTAS COM LEFT E RIGHT JOIN (Mínimo 4)<br>
	- select classe.id, classe.tipo, imovel.codigo from Classe left outer join Imovel on (classe.id = imovel.fk_classe_id)order by tipo ASC
	- select estado.id, estado.nome, imovel.codigo from Estado left outer join Imovel on (estado.id = imovel.fk_estado_id)order by nome ASC
	- select bairro.id, bairro.nome, imovel.codigo from Bairro left outer join Imovel on (bairro.id = imovel.fk_bairro_id)order by nome ASC
	- select tipo.id, tipo.tipo, contato.codigo from Tipo left outer join Contato on (tipo.id = contato.fk_tipo_id)order by tipo ASC
	
#### 9.9	CONSULTAS COM SELF JOIN E VIEW (Mínimo 6)<br>
	a) Junções com views que o grupo considere importante para o trabalho:
	- create view nome_e_rg_supervisor as select nome,rg from supervisor;
	- create view nome_e_rg_cliente as select nome,rg from cliente;
	- create view temp_hora_fk_imovel as select temperatura,hora,fk_imovel_codigo from Registro;
	- create view tipo_contato_id as select id,tipo from tipo;
	- create view contato_cliente_rg as select fk_cliente_rg,contato from contato;

#### 9.10	SUBCONSULTAS (Mínimo 3)<br>
	- SELECT IMOVEL.Codigo, CLASSE.Tipo, CATEGORIA.Tipo, REGISTRO.Data, REGISTRO.Temperatura FROM IMOVEL
	INNER JOIN CLASSE ON (IMOVEL.FK_CLASSE_ID = CLASSE.ID)
	INNER JOIN REGISTRO ON (IMOVEL.Codigo = REGISTRO.FK_IMOVEL_Codigo)
	INNER JOIN CATEGORIA ON (REGISTRO.FK_CATEGORIA_Codigo = CATEGORIA.Codigo) WHERE CATEGORIA.Tipo IN (SELECT Tipo FROM CATEGORIA 		WHERE Tipo <> 'Residencial');

	-
	-

#### 9.11	LISTA DE CODIGOS DAS FUNÇÕES E TRIGGERS<br>
        Detalhamento sobre funcionalidade de cada código.
        a) Objetivo
        b) Código do objeto (função/trigger)
        c) exemplo de dados para aplicação
        d) resultados em forma de tabela/imagem
<br>


#### 9.12	GERACAO DE DADOS (MÍNIMO DE 100 MIL REGISTROS PARA PRINCIPAL RELAÇAO)<br>
        a) principal tabela do sistema deve ter no mínimo 100 mil registros
        b) tabelas diretamente relacionadas a tabela principal 10 mil registros
        c) tabelas auxiliares de relacao multivalorada mínimo de 10 registros
        d) registrar o tempo de inserção em cada uma das tabelas do banco de dados
        e) especificar a quantidade de registros inseridos em cada tabela
        Para melhor compreensão verifiquem o exemplo na base de testes:<br>
        https://github.com/discipbd2/base-de-testes-locadora
        

#### 9.13	Backup do Banco de Dados<br>
        Detalhamento do backup.
        a) Tempo
        b) Tamanho
        c) Teste de restauração (backup)
        d) Tempo para restauração
        e) Teste de restauração (script sql)
        f) Tempo para restauração (script sql)
<br>

Data de Entrega: (Data a ser definida)
<br>

#### 9.14	APLICAÇAO DE ÍNDICES E TESTES DE PERFORMANCE<br>
    a) Lista de índices, tipos de índices com explicação de porque foram implementados nas consultas 
    b) Performance esperada VS Resultados obtidos
    c) Tabela de resultados comparando velocidades antes e depois da aplicação dos índices (constando velocidade esperada com planejamento, sem indice e com índice Vs velocidade de execucao real com índice e sem índice).
    d) Escolher as consultas mais complexas para serem analisadas (consultas com menos de 2 joins não serão aceitas)
    e) As imagens do Explain devem ser inclusas no trabalho, bem como explicações sobre os resultados obtidos.
    f) Inclusão de tabela mostrando as 10 execuções, excluindo-se o maior e menor tempos para cada consulta e 
    obtendo-se a media dos outros valores como resultado médio final.
<br>
    Data de Entrega: (Data a ser definida)
<br>   

### 10	ATUALIZAÇÃO DA DOCUMENTAÇÃO DOS SLIDES PARA APRESENTAÇAO FINAL (Mínimo 6 e Máximo 10)<br>
<br>
    Data de Entrega: (Data a ser definida)
<br>

### 11 Backup completo do banco de dados postgres 
    a) deve ser realizado no formato "backup" 
        (Em Dump Options #1 Habilitar opções Don't Save Owner e Privilege)
    b) antes de postar o arquivo no git o mesmo deve ser testado/restaurado por outro grupo de alunos/dupla
    c) informar aqui o grupo de alunos/dupla que realizou o teste.

    
### 12	TUTORIAL COMPLETO DE PASSOS PARA RESTAURACAO DO BANCO E EXECUCAO DE PROCEDIMENTOS ENVOLVIDOS NO TRABALHO PARA OBTENÇÃO DOS RESULTADOS<br>
        a) Outros grupos deverão ser capazes de restaurar o banco 
        b) executar todas as consultas presentes no trabalho
        c) executar códigos que tenham sido construídos para o trabalho 
        d) realizar qualquer procedimento executado pelo grupo que desenvolveu o trabalho

### 13	DIFICULDADES ENCONTRADAS PELO GRUPO<br>  

    
Data de Entrega final: (Data a ser definida)
<br>

       
### 14  FORMATACAO NO GIT: https://help.github.com/articles/basic-writing-and-formatting-syntax/
<comentario no git>
    
##### About Formatting
    https://help.github.com/articles/about-writing-and-formatting-on-github/
    
##### Basic Formatting in Git
    
    https://help.github.com/articles/basic-writing-and-formatting-syntax/#referencing-issues-and-pull-requests
   
    
##### Working with advanced formatting
    https://help.github.com/articles/working-with-advanced-formatting/

#### Mastering Markdown
    https://guides.github.com/features/mastering-markdown/

### OBSERVAÇÕES IMPORTANTES

#### Todos os arquivos que fazem parte do projeto (Imagens, pdfs, arquivos fonte, etc..), devem estar presentes no GIT. Os arquivos do projeto vigente não devem ser armazenados em quaisquer outras plataformas.
1. Caso existam arquivos com conteúdos sigilosos, comunicar o professor que definirá em conjunto com o grupo a melhor forma de armazenamento do arquivo.

#### Todos os grupos deverão fazer Fork deste repositório e dar permissões administrativas ao usuário deste GIT, para acompanhamento do trabalho.

#### Os usuários criados no GIT devem possuir o nome de identificação do aluno (não serão aceitos nomes como Eu123, meuprojeto, pro456, etc). Em caso de dúvida comunicar o professor.


Link para BrModelo:<br>
http://sis4.com/brModelo/brModelo/download.html
<br>


Link para curso de GIT<br>
![https://www.youtube.com/curso_git](https://www.youtube.com/playlist?list=PLo7sFyCeiGUdIyEmHdfbuD2eR4XPDqnN2?raw=true "Title")


        
        


    





