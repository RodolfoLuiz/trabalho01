# TRABALHO 01:  ANTI-FIRE DETECTOR
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
+ Relatório de clientes incluindo as seguintes informações: rg do cliente, nome do cliente, data de nascimento do cliente, sexo do cliente e cpf do cliente; 
+ Relatório de Incidentes ocorridos no mês: A categoria dos incidentes, a data, o imovel em que ocorreu ;
+ Relatório de tipo de imóveis que mais ocorrem incêndios incluindo as seguintes informações:  tipo do imóvel, numero de comodos e quantidade de vezes que o sistema é acionado;
+ Relatório dos pacotes mais comprados incluindo: tipo do imóvel, numero de comodos, valor do pacote, pacote mais comprado;
+ Relatório do estado onde mais é vendido: estado com mais clientes, numero de clientes.


#### 4.2 TABELA DE DADOS DO SISTEMA:
![Tabela de dados da Empresa Anti-Fire Company ](https://github.com/RodolfoLuiz/trabalho01/blob/master/Tabela%20BRABA%20FINALizada.ods)

    
### 5.MODELO CONCEITUAL<br>
    A) NOTACAO ENTIDADE RELACIONAMENTO 
        * Para nosso prótótipo limitaremos o modelo conceitual nas 5 principais entidades do escopo
        * O protótipo deve possui no mínimo duas relações N para N
        
![Alt text](https://github.com/RodolfoLuiz/trabalho01/blob/master/modelo%20Conceitual%202009.png)
    
    B) QUALIDADE 
        Garantir que a semântica dos atributos seja clara no esquema
        Criar o esquema de forma a garantir a redução de informação redundante, possibilidade de valores null, 
        e tuplas falsas
    
        
    
#### 5.1 Validação do Modelo Conceitual
    [Grupo01]: [Calebe Carias e Davi Moura]
    [Grupo02]: [Júlia Suzano e Beatriz Auer]
    
    

#### 5.2 DESCRIÇÃO DOS DADOS 
CLIENTE: Tabela que armazena as informações referentes aos clientes.<br>
NOME: Campo que armazena o nome de cada cliente da empresa.<br>
E-MAIL: Campo que armazena o e-mail dos clientes.<br>
TELEFONE:  Campo que armazena o telefone de contato dos clientes.<br>
RG: Campo que armazena o Registro Geral dos clientes.<br>
CPF: Campo que armazena o número de Cadastro de Pessoa Física de cada cliente da empresa.<br>
DATA_NASC: Campo que armazena a data de nascimento dos clientes.<br>
IMOVEL: Tabela que armazena as informações referentes aos imóveis cadastrados pelos clientes.<br>
CODIGO: Campo que armazena o código identificador de cada imóvel cadastrado. <br>
ENDERECO:  Campo que armazena as informações relativas a localização, endereço de cada imóvel cadastrado.<br>
TIPO: Campo que armazena o tipo do imóvel cadastrado. Por exemplo: Comercial, Residencial, Industrial. <br>
NUM_COMODOS: Campo que armazena o número de cômodos existentes em cada imóvel.<br>
PRECO_PACOTE: Campo que armazena o preço do pacote, escolhido pelo cliente, para determinado imóvel.<br>
DATA_INSTALACAO: Campo que armazena a data em que ocorreu a instalação no imóvel. Este dado não é inserido/definido pelo usuário.<br>
DATA_MANUTENCAO: Campo que armazena a data da última manutenção realizada no imóvel. <br>
SENSORES: Tabela que armazena as informações, fornecidas pelos sensores, referentes aos incidentes (Ex.: Incedio, Vazamento de gás, etc) ocorridos em cada um dos imóveis cadastrados.<br>
DATA: Campo que armazena a data dos incidentes.<br>
TEMPERATURA: Campo que armazena a temperatura máxima registrada pelos sensores durante o incidente.<br>
HORA:  Campo que armazena o horário em que os sensores foram acionados, e detectaram o incidente.<br>
CATEGORIA: Campo que armazena a categoria/tipo do incidente(Ex.: Incedio, Vazamento de gás, etc).<br>
UMIDADE: Campo que armazena a umidade registrada pelos sensores durante o incidente.<br>
ID: Campo que armazena o identificador dos sensores.<br>
 
### 6	MODELO LÓGICO<br>
  ![Alt text](https://github.com/RodolfoLuiz/trabalho01/blob/master/modelo%20logico%202009.png)

### 7	MODELO FÍSICO<br>
  ![Alt text](https://github.com/RodolfoLuiz/trabalho01/blob/master/F%C3%8DSICO%2B.png)       


### 8	INSERT APLICADO NAS TABELAS DO BANCO DE DADOS<br>
#### 8.1 DETALHAMENTO DAS INFORMAÇÕES
        

insert into Cliente(nome, cpf, rg, telefone, email, data_nasc)

values('Jobiscleiton', '111222333-00', '11 111 111-1', '1111-1111', 'jobis@gmail.com', '01-01-1950'),
('Gustavo', '111222333-01',  '22 222 222-2', '2222-2222', 'gustavo@gmail.com', '02-02-1987'),
('Calebe', '111222333-02', '33 333 333-3', '3333-3333', 'cabele@hotmail.com', '10-02-1981'),
('Pedro', '111222333-03', '44 444 444-4', '4444-4444', 'pedro@gmail.com', '19-02-1976');      
	   

insert into Imovel(tipo, num_comodos, data_instalacao, data_manutencao, endereco, preco_pacote, codigo)

values ('Industrial', 3, '1-1-2019', '1-2-2019','ES-Serra- Rua 1A- Nº31',  '400',110),
('Residencial',4, '2-2-2019', '2-3-2019','ES-Serra- Rua 1B- Nº45',  '300',220),
('Comercial',  5, '3-3-2019', '3-4-2019','ES-Serra- Rua 5F- Nº86',  '600',330),
('Comercial',  4, '4-4-2019', '4-5-2019','ES-Vitória- Rua 6A- Nº49','600',440);


insert into Sensores(data, temperatura, hora, categoria, umidade, cod_imovel, id)

values('1-2-2020', '22ºC', '13:30', 'VAZAMENTO DE GÁS', '70', 110, 120S),
      ('2-3-2020', '25ºC', '12:00', 'VAZAMENTO DE GÁS', '70', 220, 230S),
      ('3-4-2020', '23ºC', '12:30', 'VAZAMENTO DE GÁS', '70', 330, 340S),
      ('4-5-2020', '16ºC', '18:40', 'VAZAMENTO DE GÁS', '70', 440, 450S);
	  


#### 8.2 INCLUSÃO DO SCRIPT PARA CRIAÇÃO DE TABELA E INSERÇÃO DOS DADOS
create table Cliente(nome varchar(40), cpf varchar(25), rg varchar(25) PRIMARY KEY,telefone varchar(15), email varchar(40), data_nasc date);

create table cliente_imovel(Cliente_rg varchar(40), codigo_imovel varchar(40);

create table Imovel(tipo varchar(40), num_comodos integer, data_instalacao date, data_manutencao date, endereco varchar(40), preco_pacote varchar(40), codigo varchar(40) PRIMARY KEY);

create table Sensores (data date, temperatura float, hora time, categoria varchar(40), umidade float, cod_imovel varchar(40) PRIMARY KEY, id varchar(30));

select * from Cliente

select * from cliente_imovel

select * from Imovel

select * from Sensores        
        
        
        
#### 8.3 INCLUSÃO DO SCRIPT PARA EXCLUSÃO DE TABELAS EXISTENTES, CRIAÇÃO DE TABELA NOVAS E INSERÇÃO DOS DADOS
drop table Cliente

drop table Imovel

drop table Sensores

drop table cliente_imovel

create table Cliente(nome varchar(40), cpf varchar(25), rg varchar(25) PRIMARY KEY,telefone varchar(15), email varchar(40), data_nasc date);

create table Imovel(tipo varchar(40), num_comodos integer, data_instalacao date, data_manutencao date, endereco varchar(40), preco_pacote varchar(40), cod_imovel varchar(40) PRIMARY KEY);

create table Sensores (data date, temperatura float, hora time, categoria varchar(40), umidade float, cod_imovel varchar(40) PRIMARY KEY, id varchar(30));

create table cliente_imovel(Cliente_rg varchar(40), codigo_imovel varchar(40);


insert into Cliente(nome, cpf, rg, telefone, email, data_nasc)

values('Jobiscleiton', '111222333-00', '11 111 111-1', '1111-1111', 'jobis@gmail.com', '01-01-1950'),
      ('Gustavo', '111222333-01',  '22 222 222-2', '2222-2222', 'gustavo@gmail.com', '02-02-1987'),
      ('Calebe', '111222333-02', '33 333 333-3', '3333-3333', 'cabele@hotmail.com', '10-02-1981'),
      ('Pedro', '111222333-03', '44 444 444-4', '4444-4444', 'pedro@gmail.com', '19-02-1976');      
	   

insert into Imovel(tipo, num_comodos, data_instalacao, data_manutencao, endereco, preco_pacote, cod_imovel)

values ('Industrial', 3, '1-1-2019', '1-2-2019','ES-Serra- Rua 1A- Nº31',  '400',110),
       ('Residencial',4, '2-2-2019', '2-3-2019','ES-Serra- Rua 1B- Nº45',  '300',220),
       ('Comercial',  5, '3-3-2019', '3-4-2019','ES-Serra- Rua 5F- Nº86',  '600',330),
       ('Comercial',  4, '4-4-2019', '4-5-2019','ES-Vitória- Rua 6A- Nº49','600',440);


insert into Sensores(data, temperatura, hora, categoria, umidade, cod_imovel, id)

values('1-2-2020', '22ºC', '13:30', 'VAZAMENTO DE GÁS', '70', 110, 120S),
      ('2-3-2020', '25ºC', '12:00', 'VAZAMENTO DE GÁS', '70', 220, 230S),
      ('3-4-2020', '23ºC', '12:30', 'VAZAMENTO DE GÁS', '70', 330, 340S),
      ('4-5-2020', '16ºC', '18:40', 'VAZAMENTO DE GÁS', '70', 440, 450S);
	  
select * from Cliente

select * from Imovel																														 
select * from Sensores

select * from cliente_imovel


### 9	TABELAS E PRINCIPAIS CONSULTAS<br>
    OBS: Incluir para cada tópico as instruções SQL + imagens (print da tela) mostrando os resultados.<br>
#### 9.1	CONSULTAS DAS TABELAS COM TODOS OS DADOS INSERIDOS (Todas) <br>
![Alt text](https://github.com/RodolfoLuiz/trabalho01/blob/master/printTableCliente15.png)    
![Alt text](https://github.com/RodolfoLuiz/trabalho01/blob/master/printTableImovel15.png)   
![Alt text](https://github.com/RodolfoLuiz/trabalho01/blob/master/printTableSensor15.png)   
	
#### 9.2	CONSULTAS DAS TABELAS COM FILTROS WHERE (Mínimo 4)<br>
#### 9.3	CONSULTAS QUE USAM OPERADORES LÓGICOS, ARITMÉTICOS E TABELAS OU CAMPOS RENOMEADOS (Mínimo 11)
    a) Criar 5 consultas que envolvam os operadores lógicos AND, OR e Not
    b) Criar no mínimo 3 consultas com operadores aritméticos 
    c) Criar no mínimo 3 consultas com operação de renomear nomes de campos ou tabelas
#### 9.4	CONSULTAS QUE USAM OPERADORES LIKE E DATAS (Mínimo 12) <br>
    a) Criar outras 5 consultas que envolvam like ou ilike
    b) Criar uma consulta para cada tipo de função data apresentada.


    
#### 9.5	ATUALIZAÇÃO E EXCLUSÃO DE DADOS (Mínimo 6)<br>


#### 9.6	CONSULTAS COM JUNÇÃO E ORDENAÇÃO (Mínimo 6)<br>
        a) Uma junção que envolva todas as tabelas possuindo no mínimo 3 registros no resultado
        b) Outras junções que o grupo considere como sendo as de principal importância para o trabalho
        

### ATUALIZAÇÃO DA DOCUMENTAÇÃO DOS SLIDES PARA APRESENTAÇAO SEMESTRAL (Mínimo 6 e Máximo 10)<br>


#### 9.7	CONSULTAS COM GROUP BY E FUNÇÕES DE AGRUPAMENTO (Mínimo 6)<br>

#### 9.8	CONSULTAS COM LEFT E RIGHT JOIN (Mínimo 4)<br>
#### 9.9	CONSULTAS COM SELF JOIN E VIEW (Mínimo 6)<br>
        a) Uma junção que envolva Self Join
        b) Outras junções com views que o grupo considere como sendo de relevante importância para o trabalho
#### 9.10	SUBCONSULTAS (Mínimo 3)<br>

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


        
        


    





