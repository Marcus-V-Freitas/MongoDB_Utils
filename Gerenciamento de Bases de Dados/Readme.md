# Escolher Base de Dados

//Criar e/ou escolher base de dados
use meuBanco

//Verificar Banco de Dados Atual
db

//Mostrar todos os dbs
show dbs


# Inserir e criar coleções de forma explícita
# Exemplo

db.Funcionarios.insertOne({nome: "Lucas", salario: 4000})
db.Funcionarios.insertOne({nome: "Maria", salario: 6500})

//retornar todos os resultados
db.salarios.find()

//Mostrar todas as coleções
show collections

# Coleções implícitas

// capped é necessario, 1000 bytes, Máximo de 60 registros
db.createCollection("minhacolecao", {capped: true, size: 1000 max: 60})  

# Importar Dados (Uma única coleção)

//mongoimport <arquivo> -d <nome do banco> -c <nome da coleção>

mongoimport books.json -d livraria -c livros

# Exportar Dados 

//mongoexport -c <nome da coleção>  -d <nome do banco> -o arquivo de saída

mongoexport -c livros -d livraria -o livrosExemplo.json

# Exportar muitas collections - mongodump

use meuBanco

db.pessoas.insertOne({nome: "Ricardo", idade: 40})

db.enderecos.insertOne({rua: "Avenida Brasil", numero: "1243"})

mongodump -d meuBanco -o meuBanco

# importar arquivos do mongodump

mongorestore <diretorio>

# Monitoramento do MongoDB

mongostat

Serve para checar informações como quantidades de consultas, consumo de rede e outros dados (Deve ser feito em aba separada pois roda em segundo plano)

 