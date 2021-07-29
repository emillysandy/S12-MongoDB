# Turma On12 - Reprograma - Semana 12

Atividade de manipulação de banco de dados com MongoDB.

## Temos um lista de contatos de alunas da Reprograma e queremos controlar

### Criação de novo database
`use reprograma`

### Criação de nova collection
`db.createCollections('alunas')`

### Inserindo documentos na collection
`
db.alunas.insertMany([
  "Beyoncé": {
    " id " : " 1 " ,
    " nome " : " Bey " ,
    " celular " : " (11) 99178630 " ,
    " redesSociais " : " @beyonce ",
    " atividade 9" : " ENTREGUE ",
    " atividade 10" : " PENDENTE ",
    " atividade 11" : " ENTREGUE ",
    " atividade 12" : " PENDENTE "
   },
  "Rihanna": {
    " id " : " 2 " ,
    " nome " : " Riri " ,
    " celular " : " (21) 983729320 " ,
    " redesSociais " : " @ riri10_10 ",
    " atividade 9" : " ENTREGUE ",
    " atividade 10" : " ENTRGUE ",
    " atividade 11" : " ENTREGUE ",
    " atividade 12" : " ENTREGUE "
   },
   "Lady Gaga": {
    " id " : " 3 ",
    " nome " : "Gaga",
    " celular " : " (81) 984729370 ",
    " atividade 9" : " PENDENTE ",
    " atividade 10" : " PENDENTE ",
    " atividade 11" : " PENDENTE ",
    " atividade 12" : " PENDENTE "
   }
)]

`

### Consultando todas as alunas que entregaram a atividade 9

`db.getCollection('alunass').find({ atividade 9 : 'ENTREGUE'})`

### Consultando todas as alunas que entregaram a atividade 9 e ordenando por  crescente de id (consulta com projeção)

`db.getCollection('alunas').find({ atividade 9 : 'ENTREGUE'}).sort({'id': 1})`

### Consultando todas as alunas que estão com as atividades 9 e 10 PENDENTES (combinando seletores)

`db.getCollection('alunas').find({ atividade 9 : 'PENDENTE', atividade 10 : 'PENDENTE'})`

### Atualizando atividade 9 da aluna Lady Gaga

`
db.getCollection('alunas').update(
    { " nome " : "Gaga" },
    { $set:
        { 
            " atividade 9" : " ENTREGUE " 
        }
    }
);
`
### Deletando atividades 11 que não foram entrgues

`db.getCollection('alunas').remove({ atividade 11 : { $ne: "ENTREGUE"}})`
