# Preparação Ambiente Docker com SQL Server

Pessoal,

Durante a aula foram apresentadas as ferramentas que usaremos em nosso curso para as ATIVIDADES DE AVALIAÇÃO (INDIVIDUAL) e TRABALHO FINAL (GRUPO). Primordialmente, precisaremos de um banco de dados para estruturar e manipular os dados. Consequentemente, esse banco de dados requer seu armazenamento em SGBD e neste curso será o SQL Server.

#
## A) Inicie o download (e a instalação) dos seguintes executáveis:


### OBS.: Lembre-se de efetuar o download correto para cada instalação conforme seu sistema operacional (Windows, Mac ou Linux).


1. Docker Desktop (Procedimento específico em cada link)
    1. Windows - https://docs.docker.com/desktop/windows/install/
    2. Mac - https://docs.docker.com/desktop/mac/install/
    3. Linux - https://docs.docker.com/engine/install/#server
2. Azure Data Studio - https://docs.microsoft.com/pt-br/sql/azure-data-studio/download-azure-data-studio


#
## B) Em seguida, faça download dos arquivos abaixo:


### OBS.: Faremos download dos arquivos referentes aos arquivos 2017, compatível com a versão do SQL Server 2017 em Docker.


1. AdventureWorks (OLTP) - https://github.com/Microsoft/sql-server-samples/releases/download/adventureworks/AdventureWorks2017.bak
2. AdventureWorksDW (OLAP) - https://github.com/Microsoft/sql-server-samples/releases/download/adventureworks/AdventureWorksDW2017.bak

#
## C) Com os downloads finalizados,  execute as etapas a seguir:


	
Procedimento baseado na Documentação Oficial do Microsoft SQL Server em Docker conforme pode ser visto em 
https://hub.docker.com/_/microsoft-mssql-server.


1. Primeiro, execute no seu terminal:  docker -v
2. Esse comando deve ter um retorno semelhante a “Docker version 20.10.8, build 3967b7d”.
3. Após a execução do Passo 1, execute no seu terminal:
    1. docker run -e "ACCEPT_EULA=Y" -e "SA_PASSWORD=yourStrong(!)Password" -p 1433:1433 -d mcr.microsoft.com/mssql/server:2017-latest
    2. A execução do Passo 3.1, deve durar entre 5 e 10min (Internet 200MB)
    3. Agora para verificar o contêiner criado, execute no seu terminal: docker ps
    3.1. Se os passos 1 e 2 forem executados corretos, aparecerá no resultado: 
    		--> CONTEINER ID com um hash (por exemplo, "0c4a1a032e02"), IMAGE (contendo "mcr.microsoft.com/mssql/server") e outros campos. 	 
4. Agora vamos conectar o Azure Data Studio (ADS) ao contêiner mssql 
5. Abra o ADS
6. Siga os passos descritos em https://docs.microsoft.com/pt-br/sql/azure-data-studio/quickstart-sql-server?view=sql-server-ver15#connect-to-a-sql-server para preencher as informações de acordo com a imagem dos detalhes de conexão abaixo:

    ![Detalhes de conexão](https://docs.microsoft.com/pt-br/sql/azure-data-studio/media/quickstart-sql-server/new-connection-screen.png?view=sql-server-ver15)

1. No campo “Servidor” coloque **localhost**
2. No campo “Nome do usuário” adicione **sa**
3. No campo “Senha” coloque o conteúdo usado no Passo 3: **yourStrong(!)Password** (em SA_PASSWORD)
    
