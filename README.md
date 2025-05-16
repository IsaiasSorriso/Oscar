🏆 Banco de Dados dos Indicados ao Oscar
Este repositório contém uma base de dados completa dos indicados ao Oscar em formato MongoDB, perfeito para praticar operações CRUD e análises de dados.

📊 Estatísticas Principais
Total de registros: 11,004 indicações

Indicações por categoria:

DIRECTING: 474

FILM EDITING: 450

ACTOR IN A SUPPORTING ROLE: 445

ACTRESS IN A SUPPORTING ROLE: 440

BEST PICTURE: 381

🎭 Destaques de Atores
Ator/Atriz	Indicações	Oscars Ganhos
Natalie Portman	3	1
Viola Davis	4	1
Amy Adams	-	0
Denzel Washington	-	2
Sidney Poitier	-	Primeiro ator negro indicado (1959)
🎬 Filmes Notáveis
Toy Story ganhou Oscars em: 2011 e 2020

Crash concorreu na 78ª edição

Central do Brasil não aparece nos registros

Filmes que mereciam indicação:

Deu a Louca na Chapeuzinho (2004)

As Branquelas (2003)

A Fuga das Galinhas (1999)

🔍 Consultas Interessantes
javascript
// Primeira Melhor Atriz
db.registros.find({
  categoria: "ACTRESS",
  vencedor: 1
}).sort({ ano_cerimonia: 1 }).limit(1)
// Resultado: Janet Gaynor em 1928

// Filmes com Melhor Filme E Diretor
db.registros.aggregate([
  { $match: { 
    categoria: { $in: ["BEST MOTION PICTURE", "DIRECTING"] }, 
    vencedor: 1 
  }},
  { $group: { 
    _id: { cerimonia: "$cerimonia", filme: "$nome_do_filme" }, 
    categorias: { $addToSet: "$categoria" } 
  }},
  { $match: { 
    categorias: { $all: ["BEST MOTION PICTURE", "DIRECTING"] } 
  }}
])
⚙️ Atualizações Recentes
Valores booleanos convertidos para numéricos (1/0)

Dados do Oscar 2025 incluídos

3 filmes notáveis adicionados à base

📅 Curiosidades Históricas
A categoria "ACTRESS" deixou de existir em 1928

Sidney Poitier foi o primeiro ator negro indicado (1959)

Denzel Washington e Jamie Foxx nunca concorreram no mesmo ano
