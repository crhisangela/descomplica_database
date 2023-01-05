# Banco de dados


**Database:** um modo estruturado de guardar e acessar dados armazenados

# SQL
    
    CRIAR banco de dados: `CREATE DATABASE SUCOS`
    APAGAR um banco de dados: `DROP DATABASE SUCOS`

# NoSQL

**NoSQL Database**: qualquer base de dados que não armazena/organiza os dados em tabela (linhas e colunas)

**NoSQL DocumentDB:** dados no mongo DB são armazenados em documentos e organizados em coleções. 

    Com o formato JSON, sempre teremos objetos de Chave-Valor, onde podemos observar alguns pontos característicos:

    - As chaves são do tipo “String”.

    - O delimitador entre Chave-Valor é o “:” (dois pontos).

    - Cada entrada “Chave-Valor” é separada por “,” (vigula).

    - Cada objeto JSON é delimitado por “{}” (Chaves).



# MongoDB

## Primeiros passos (CRuD): 

[Criando uma collection e adicionando informações: ](https://www.mongodb.com/docs/manual/reference/method/db.collection.createIndex/#db.collection.createIndex)

### **INSERT**:

```db.NOMEDACOLLECTION.insert({FIELD: "VALUE", FIELD2: VALUE2"})```

Exemplo:

```db.users.insert({ name: "Crhis Ferreira", email: "crhis@gmail.com", age: 22})```

```db.users.insertOne( { name: "crhis", age: 22 } ) ```

```db.users.insertMany( [{ name: "ruth", age: 45 }, { name: "alecs", qty: 23 }, { name: "junior" , age: 40 } ] )```


### **READ**:

```db.users.find()```     -->> retorna tudo da collection

Exemplo:

```db.users.find({age: {$gte: 23})```

`db.users.findOne({age: {$gte: 23})`   --> retorna a primeira ocorrencia da busca

### **DELETE**:

`db.users.delete()`

Exemplo:

`db.users.remove({age: 23}, {justOne: True})  `  --> remover a primeira ocorrencia da busca

`db.users.remove({age: {$gte: 23}}`)              --> remover todos com idade >= 23

`db.users.deleteMany({age: {$gte: 25, $lte:44}})` --> remover todos com idade >= 25 e <= 44



## Operadores básicos:


**count()**: contar a quantidade de documentos que uma consulta irá retornar. EX: `db.NomeColeção.find({condição}, {atributos exibidos ou não}).count()`

**find():** fazer consultas.  EX: `db.getCollection("products").find({ $or : [{"comida": "banana"}, {"comida": "pudim"} ] })`

**$limit:** para limitar a quantidade de documentos retornados

**$sort:** ordem que você quer a sua consulta → 1 = ordem crescente  ;   -1 = ordem decrescente. 

**$and:** operador lógico AND

**$or:** – operador lógico OR

**$not:** operador lógico NOT

**$gt:** maior que

**$lt:** menor que

**$gte:** maior ou igual

**$lte:** menor ou igual

**$ne:** diferente de

**$in:** todos os documentos cujo atributo possui um dos valores especificados (no SQL operador IN)

**$nin:** todos os documentos cujo atributo não possui um dos valores especificados (no SQL operador NOT IN)


By: **sıɥɹƆ sıɥɹƆ**
