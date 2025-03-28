# Projeto de Consulta e Filtragem de Dados com MongoDB e Pandas

Este projeto tem como objetivo realizar a extração, transformação e visualização de dados a partir de coleções armazenadas em uma base MongoDB Atlas, utilizando a linguagem Python e a biblioteca Pandas.

## Tecnologias Utilizadas

- Python 3.x
- Pandas
- PyMongo
- MongoDB Atlas

## Coleções Utilizadas

O projeto utiliza as seguintes coleções:

- `cliente`
- `fornecedor`
- `banco`
- `pagamento`
- `recebimento`

Cada uma dessas coleções contém informações específicas:

### Exemplo de documento da coleção `cliente`:

```json
{
  "_id": ObjectId("..."),
  "Id Cliente": 1,
  "Razao Social": "00_VPCOM",
  "Nome Fantasia": "VENTOS POTIGUARES COMERCIALIZADORA...",
  "Tipo Pessoa": "Pessoa Física",
  "Municipio": "SAO PAULO",
  "UF": "SÃO PAULO"
}
```

## Funcionalidades Implementadas

### ✅ Consulta: Clientes da cidade de São Paulo

```python
df_clientes_sp = df_clientes[df_clientes['Municipio'].str.upper() == 'SAO PAULO']
print(df_clientes_sp)
```

---

### ✅ Consulta: Fornecedores Pessoa Física

```python
df_fornecedores_pf = df_fornecedores[df_fornecedores['Tipo Pessoa'] == 'Pessoa Física']
print(df_fornecedores_pf)
```

---

### ✅ Consulta: Todos os recebimentos

```python
df_recebimentos = pd.DataFrame(recebimentos_data)
print(df_recebimentos)
```

---

### ✅ Consulta: Todos os pagamentos

```python
df_pagamentos = pd.DataFrame(pagamentos_data)
print(df_pagamentos)
```

---

## Conectando-se ao MongoDB Atlas

O projeto realiza a conexão ao cluster do MongoDB Atlas com `pymongo.MongoClient` para coletar os dados das coleções dinamicamente e gerar os DataFrames a partir disso.

---

## Contato

- [LinkedIn - Felipe Souza de Oliveira](https://www.linkedin.com/in/felipe-souza-de-oliveira/)
- [GitHub - felipeeng23](https://github.com/felipeeng23)