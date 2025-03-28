# MongoDB - Projeto de Integração e Consultas com Pandas

Este repositório tem como objetivo demonstrar a integração entre um banco de dados **MongoDB Atlas** e o ambiente **Python** com uso do **pandas**, para fins de manipulação, análise e exibição de dados estruturados em coleções.

## 🔍 Sobre o Projeto

Foram utilizadas cinco coleções principais:

- `cliente`
- `fornecedor`
- `pagamento`
- `recebimento`
- `banco`

O projeto realiza a conexão com o MongoDB Atlas, consulta os dados das coleções e aplica filtros ou transformações conforme a necessidade, exibindo os resultados em DataFrames pandas.

## 🛠️ Tecnologias Utilizadas

- Python 3.x
- Pandas
- PyMongo
- MongoDB Atlas

## 📁 Estrutura das Coleções (Exemplos de Documentos)

### 🧾 Cliente
```json
{
  "Id Cliente": 1,
  "Razao Social": "00_VPCOM",
  "Nome Fantasia": "VENTOS POTIGUARES COMERCIALIZADORA...",
  "Tipo Pessoa": "Pessoa Física",
  "Municipio": "SAO PAULO",
  "UF": "SÃO PAULO"
}
```

### 🧾 Fornecedor
```json
{
  "Id Fornecedor": 1,
  "Razao Social": "AGROBOI",
  "Nome Fantasia": "AGRO BOI IMPORTACAO E EXPORTACAO...",
  "Tipo Pessoa": "Pessoa Jurídica",
  "Municipio": "RIO DE JANEIRO",
  "UF": "RIO DE JANEIRO"
}
```

### 💰 Pagamento
```json
{
  "Id Fornecedor": 9,
  "Id Conta Bancária": "x 80771218846-00",
  "Data de Emissao": "1/11/2018",
  "Data de Vencimento": "1/16/2018",
  "Data da Movimentação": "1/11/2018",
  "Valor da Movimentação": "19540,71"
}
```

### 💵 Recebimento
```json
{
  "Id Cliente": 53,
  "Id Conta Bancária": "x 10859524552-06",
  "Data de Emissao": "1/2/2018",
  "Data de Vencimento": "1/2/2018",
  "Data da Movimentação": "1/2/2018",
  "Valor da Movimentação": "675,87"
}
```

### 🏦 Banco
```json
{
  "Id Banco": 1,
  "Id Conta Bancária": "x 14057272557-06",
  "Nome Banco": "BANCO DO BRASIL - SAO PAULO",
  "Município": "SAO PAULO",
  "UF": "SÃO PAULO"
}
```

## 📊 Exemplos de Consultas

### ✅ Clientes de São Paulo
```python
df_clientes_sp = df_clientes[df_clientes['Municipio'].str.upper() == 'SAO PAULO']
```

### ✅ Fornecedores Pessoa Física
```python
df_fornecedores_pf = df_fornecedores[df_fornecedores['Tipo Pessoa'] == 'Pessoa Física']
```

### ✅ Todos os Recebimentos
```python
df_recebimentos = pd.DataFrame(list(colecao_recebimento.find({})))
```

### ✅ Todos os Pagamentos
```python
df_pagamentos = pd.DataFrame(list(colecao_pagamento.find({})))
```

## ⚙️ Como Executar

1. Clone o repositório:
   ```bash
   git clone https://github.com/seu-usuario/nome-do-repositorio.git
   cd nome-do-repositorio
   ```

2. Instale as dependências:
   ```bash
   pip install pandas pymongo
   ```

3. Configure a string de conexão do MongoDB Atlas no script:
   ```python
   MongoClient("mongodb+srv://<usuario>:<senha>@<seu_cluster>.mongodb.net/")
   ```

4. Execute os scripts desejados.

## 📌 Observações

- Certifique-se de que seu cluster no MongoDB Atlas está ativo e com IP autorizado.
- Os dados sensíveis foram removidos por questões de segurança.

## 📬 Contato

Caso tenha dúvidas ou sugestões, entre em contato via [seu e-mail ou LinkedIn].
