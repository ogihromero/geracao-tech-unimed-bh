# Explorando Dados Demográficos com Serviços de Big Data na AWS
Desafio de projeto do Bootcamp na DIO ministrado por Cassiano Peres (@cassianobrexbit).

## Observações
- o Amazon Athena é um serviço de consultas interativas que permite executar consultas no Amazon S3 usando o SQL.
- Por ser serverless, não é necessário gerenciar ou dimensionar clusters, nem instalar ou manter software e hardware.
- É integrado ao AWS Glue Data Catalog, que armazena metadados sobre os dados armazenados no Amazon S3, permitindo que os usuários executem consultas em dados armazenados em vários locais.
- o Athena usa o Presto, um motor de consulta de código aberto, para executar consultas.
- Algumas boas práticas:
  - Evitar arquivos muito grandes.
  - Ler uma quantidade razoável de dados por vez.
  - Evitar muitas colunas.
  - Evitar vários arquivos pequenos.
  - Usar um formato de arquivo eficiente, como o ORC.

## Serviços utilizados nessa atividade prática
 - Amazon S3
 - Amazon Glue
 - Amazon Athena
 - Amazon QuickSight

## Etapas para desenvolvimento

### Criar bucket no Amazon S3

- Amazon S3 Console -> Buckets -> Create bucket -> Bucket name [nome_do bucket] - Create bucket
- Create folder (Criar uma pasta chamada ```/output``` e outra com o nome do seu conjunto de dados. Este nome irá definir o nome da tabela criada no Glue)
- Upload dos arquivos de dados localizados na pasta ```/data```

#### Criar Glue Crawler

- Amazon Glue Console -> Crawlers -> Add Crawler
- Source type [Data Stores] -> Crawl all folders
- Data store [S3] -> Include path [caminho do diretório dos dados de entrada]
- Create IAM Role
- Frequency [Run on demand]
- Database name [seu_nome_de_db]
- Group behavior [Create a single schema for each S3 path]
- Finish
- Databases -> Tables -> Visualizar dados das tabelas criadas

### Criar aplicação no Amazon Athena

- Query editor -> Settings -> Manage settings -> Query result location and encryption -> Browse S3 -> selecionar o bucket criado
- Selecionar Database -> criar queries (exemplos na pasta ```/src```)
- Verificar queries não salvas no bucket criado no S3
- Salavar queries -> Executar novamente -> Verificar no bucket criado no S3

#### Criando nova tabela

- Generate table DDL
- Copiar a query gerada
- Selecionar o DB e criar a nova tabela em uma nova query

### Visualizar dados no Amazon QuickSight

- Signup (caso não tenha conta) -> Escolher [Standard]
- Datasets -> Create new dataset -> Athena -> Name [NomeDoDataSet] -> Create
- Select database -> select table -> Edit or preview -> Save & visualize
- Criar visualizações selecionando colunas, criando filtros e parâmetros e selecionando Visual types para gráficos.

### Eliminar recursos
 - Exluir os elementos criados

