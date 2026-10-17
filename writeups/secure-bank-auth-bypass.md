# CTF Painel de Controle (Secure Bank) — Bypass de Autenticação via SQLi

**Categoria:** Web · **Técnicas:** SQL Injection, bypass de autenticação

> ⚠️ Writeup sanitizado: sem flag e sem IP. Foco na metodologia.

## 🎯 Desafio

Painel de controle de um "banco" fictício protegido por login. O objetivo era entrar sem credenciais válidas.

## 🧭 Metodologia

### 1. Reconhecimento
- Análise da tela de login em `<alvo do laboratório>` e do comportamento das respostas a tentativas inválidas.

### 2. Hipótese de injeção
- Query de autenticação provavelmente no formato `SELECT ... WHERE user = '...' AND senha = '...'`.
- Se a entrada não for sanitizada, é possível **alterar a lógica** da condição.

### 3. Bypass
- Injeção de um payload que torna a cláusula `WHERE` sempre verdadeira, fazendo a aplicação autenticar sem senha correta.
- Raciocínio sobre comentários SQL para descartar o restante da query original.

## 🧠 Aprendizados

- Bypass de autenticação por SQLi é sobre **manipular a lógica booleana** da query, não sobre adivinhar senha.
- Entender a query provável **antes** de testar torna o ataque muito mais rápido.

## 🛡️ Como se defende

- Queries parametrizadas (o fim da maioria das SQLi).
- Autenticação baseada em hash+salt verificado em código, não em comparação dentro da query.
- WAF e monitoramento de tentativas anômalas de login.
