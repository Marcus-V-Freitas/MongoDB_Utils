# Inserir dados (insertOne)

//db.<collection>.insertOne({dados})

* Exemplo:

db.funcionarios.insertOne({nome: "Matheus"})
db.funcionarios.insertOne({nome: "Maria", notas: [4, 9, 10]})

# Não há relação entre dados

db.colecaoMultipla.insertOne({preco: 10000})

db.colecaoMultipla.insertOne({notas: [10, 8, 5]})

db.colecaoMultipla.insertOne({disponivel: false})

db.colecaoMultipla.find()

# Inserir Muitos Dados (insertMany)

db.collection.insertMany([{nome: "Lucas", idade: 45}, {nome: "Rafael", idade: 71}])

# Forma antiga de Inserir (insert)

db.collection.insert({nome: "João", idade: 40})
db.collection.insert([{nome: "Pedro"}, {nome: "Maria"}])

# Criar próprio id

db.collection.insert({_id: "1", nome: "Julia"})

# write concern (Determinar timeout máximo para inserção em milisegundos)

db.collection.insertMany([
  {nome: "Geraldo", idade: 87}, {nome: "Carla", idade: 42}
], {w: "majority", wtimeout: 100})


# Pretty (Usado junto com o find() para retornar json indentado)

use dadosDeCarros

db.carros.insertMany([
  {_id: "c01", marca: "Ferrari", modelo: "f40", ano_fabricacao: 2012, km: 40000},
  {_id: "c02", marca: "Fiat", modelo: "Uno", ano_fabricacao: 2008, km: 150000},
  {_id: "c03", marca: "VW", modelo: "Polo", ano_fabricacao: 2019, km: 15000},
  {_id: "c04", marca: "GM", modelo: "Onix", ano_fabricacao: 2018, km: 43000}
])

db.carros.find().pretty()