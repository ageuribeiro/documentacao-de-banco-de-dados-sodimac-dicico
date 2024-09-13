## DOCUMENTAÇÃO DE ATIVIDADES DO DBA PARA IMPLANTAÇÃO DE BANCO DE DADOS NA INAUGURAÇÃO DE NOVAS LOJAS SODIMAC-DICICO

#### Este documento integra o processo de implantação do sistema de banco de dados das novas lojas. 
#### As atividades descrita no documento deevm ser executadas por um profissional especializado em SQL Server
#### Para que a implementação do banco de dados seja executada com excelência, o DBA deve se atentar aos seguintes requisitos:

### **Requisições necessárias:**

- Verificar se a equipe SAP entregou a replicação pronta do ECC Enterprise Central Component (Base de 
Dados do SAP); 
- Server2: 10.184.120.51 Servidor Central do SVC Sistema de Vendas de Contingência (Local); 
- Server1: 10.186.211.12 Servidor do ECC - replica para o Servidor 10.184.120.51; 
- Utilizando tecnologia PI o Server1 replica para o Server2 (Este processo é executado automaticamente); 
- Verificar se o nome do Banco de Dados é: DB_SVC_PII_WEB;  
- Sistema de Gerenciamento de Banco de Dados atual é o SGBD – SQL Server 2012 – Management Studio. 
- É importante que o DBA saiba que o SVC replica os dados pela tecnologia de replicação Full e replicação 
diferencial; 
- Replicação Full (Backup Completo) são todos os dados das tabelas do servidor 10.184.120.51 nas lojas 
SOLDIMAC; 
- Replicação Diferencial (Backup Diferencial) são as partes dos dados, somente o que foi alterado (Este 
processo é executado automaticamente de 15 em 15 minutos;


### __Conclusão:__
O sistema acima documentado é executado de forma automática na sua essência sendo 
necessário a intervenção do profissional apenas no momento da importação e após a finalização da 
replicação Full. 

Este processo tem a duração de aproximadamente 7 dias. Após a finalização da execução 
da atividade de replicação Full é necessário analisar os eventos conforme descrito no início deste documento. 

A cada ocorrência analisada e tratada é necessário relatar o status do sistema ao grupo de SVC 
por e-mail as seguintes informações. 
Quais os erros que aconteceram, a natureza de cada erro, e qual a 
solução, hora e data. Lembrando que os erros de script SQL dentro do banco de dados são tratados 
automaticamente. Os erros ocorridos por falha humana, ou falha de infraestrutura devem ser reportados 
ao departamento responsável, esperar a solução e após a solução, se for urgente deve ser executado uma 
intervenção manual utilizando o comando SELECT ou INSERT, ou como melhor alternativa, aguardar a 
próxima replicação de 15 minutos para equalizar os dados nas tabelas. 
Após a replicação diferencial, a cada 15 minutos, deve ser executado a análise dos eventos de serviços para 
verificar estes erros. 

