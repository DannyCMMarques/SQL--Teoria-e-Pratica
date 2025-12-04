# 📘 Resumo SQL — SELECT, WHERE, DISTINCT e ORDER BY

## 📌 1. SELECT — Buscando dados

`SELECT` é usado para **consultar dados** de uma ou mais tabelas.

### ✔ Sintaxe básica
```sql
SELECT coluna1, coluna2
FROM tabela;
```

### ✔ Selecionar tudo
```sql
SELECT *
FROM clientes;
```

### ✔ Selecionar colunas específicas
```sql
SELECT nome, email
FROM clientes;
```

### ✔ Alias (AS)
```sql
SELECT nome AS cliente, email AS contato
FROM clientes;
```

---

## 📌 2. WHERE — Filtrando dados

O `WHERE` filtra **linhas** com base em condições.

### ✔ Igualdade
```sql
WHERE status = 'PAGO'
```

### ✔ Comparações
```sql
WHERE idade > 18
WHERE preco <= 100
WHERE quantidade <> 0
```

### ✔ Operadores lógicos
```sql
WHERE categoria = 'ELETRONICO' AND preco < 1000;
WHERE cidade = 'São Paulo' OR cidade = 'Rio';
```

### ✔ BETWEEN
```sql
WHERE data_venda BETWEEN '2024-01-01' AND '2024-01-31';
```

### ✔ IN
```sql
WHERE status IN ('PAGO', 'ENVIADO', 'SEPARANDO');
```

### ✔ Nulos
```sql
WHERE telefone IS NULL;
```

---

## 📌 3. DISTINCT — Removendo duplicados

### ✔ DISTINCT simples
```sql
SELECT DISTINCT cidade
FROM clientes;
```

### ✔ DISTINCT múltiplo
```sql
SELECT DISTINCT cidade, estado
FROM clientes;
```

---

## 📌 4. ORDER BY — Ordenando resultados

### ✔ Ordem crescente
```sql
ORDER BY idade;
```

### ✔ Ordem decrescente
```sql
ORDER BY idade DESC;
```

### ✔ Múltiplas colunas
```sql
ORDER BY estado ASC, cidade ASC;
```

### ✔ Alias
```sql
SELECT nome, (2025 - ano_nascimento) AS idade
FROM clientes
ORDER BY idade DESC;
```

### ✔ ORDER BY com funções
```sql
ORDER BY UPPER(nome);
```

---

## 🎯 Mini Exercícios

### 1. Produtos de software acima de R$200:
```sql
SELECT *
FROM produtos
WHERE categoria = 'SOFTWARE'
  AND preco > 200;
```

### 2. Cidades únicas de clientes de MG:
```sql
SELECT DISTINCT cidade
FROM clientes
WHERE estado = 'MG';
```

### 3. Vendas entre junho e julho de 2025:
```sql
SELECT *
FROM vendas
WHERE data_venda BETWEEN '2025-06-01' AND '2025-07-31'
ORDER BY data_venda;
```

### 4. Clientes ordenados por idade (maior → menor):
```sql
SELECT nome, idade
FROM clientes
ORDER BY idade DESC;
```

---
