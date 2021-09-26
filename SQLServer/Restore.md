# Restauração de Backup no SQL Server via Azure Data Studio

Após concluídas as etapas pertinentes ao [Procedimento SQL Server](https://github.com/gassantos/MBA-SQLCourse/blob/main/SQLServer/Procedimento.md), será iniciar os banco de dados (OLTP e DW) a partir dos arquivos de backup **_AdventureWorks_** disponíveis para o SQL Server 2017.

Caso não tenha feito o download dos arquivos de backup mencionados, acesse os links abaixo:
* [AdventureWorks (OLTP)](https://github.com/Microsoft/sql-server-samples/releases/download/adventureworks/AdventureWorks2017.bak)
* [AdventureWorks (DW)](https://github.com/Microsoft/sql-server-samples/releases/download/adventureworks/AdventureWorksDW2017.bak)

#
## A) Enviar arquivo para MSSQL (Docker):
1. Vá até o diretório onde estão os arquivos de backup:

    Exemplo: <code>cd ~/Downloads</code>


2. Acesse o *CONTEINER_ID* do MSSQL, executando:

    <code>

    docker ps | grep mssql | awk {'print $1'} 
    </code>

3. E faça a cópia do arquivo de backup para o contêiner:

    <code>

    docker cp "diretorio-backup-file" conteiner_id:/home
    </code>

#
## B) Restaurar backup via Azure Data Studio:

