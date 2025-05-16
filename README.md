# 🏆 Banco de Dados dos Indicados ao Oscar

Este repositório contém uma base de dados completa com **11.004 registros** de indicações ao Oscar, ideal para praticar **operações CRUD em MongoDB**, fazer **análises estatísticas** e explorar **curiosidades históricas** sobre o maior prêmio do cinema mundial.

---

## 📊 Estatísticas Gerais

- **Total de registros:** `11.004` indicações
- **Categorias com mais indicações:**

  | Categoria                        | Indicações |
  |----------------------------------|------------|
  | DIRECTING                        | 474        |
  | FILM EDITING                     | 450        |
  | ACTOR IN A SUPPORTING ROLE       | 445        |
  | ACTRESS IN A SUPPORTING ROLE     | 440        |
  | BEST PICTURE                     | 381        |

---

## 🎭 Destaques de Atores e Atrizes

| Nome               | Nº de Indicações | Oscars Ganhos | Observação                                    |
|--------------------|------------------|----------------|-----------------------------------------------|
| Natalie Portman    | 3                | 1              | —                                             |
| Viola Davis        | 4                | 1              | —                                             |
| Amy Adams          | —                | 0              | Nunca ganhou                                   |
| Denzel Washington  | —                | 2              | —                                             |
| Sidney Poitier     | —                | —              | Primeiro ator negro indicado (1959)          |

---

## 🎬 Filmes Notáveis

- **Toy Story** venceu em **2011** e **2020**
- **Crash** concorreu na **78ª edição**
- **Central do Brasil** **não aparece** nos registros

**Filmes que mereciam indicação (mas não estão na base):**
- Deu a Louca na Chapeuzinho (2004)
- As Branquelas (2003)
- A Fuga das Galinhas (1999)

---

## 🔍 Consultas MongoDB Interessantes

### 🎖 Primeira atriz a vencer o Oscar
```javascript
db.registros.find({
  categoria: "ACTRESS",
  vencedor: 1
}).sort({ ano_cerimonia: 1 }).limit(1)
// Resultado: Janet Gaynor em 1928
