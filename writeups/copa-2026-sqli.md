# CTF Copa 2026 — SQL Injection no Login

**Categoria:** Web · **Técnicas:** recon, SQL Injection, análise de dump, escalada de acesso

> ⚠️ Writeup sanitizado: sem flag, sem IP e sem credenciais. Foco na metodologia.

## 🎯 Desafio

Aplicação web com tela de login. O objetivo era obter acesso privilegiado explorando uma falha de injeção.

## 🧭 Metodologia

### 1. Reconhecimento
- Mapeamento da aplicação e dos pontos de entrada (`<alvo do laboratório>`).
- Identificação do formulário de login como superfície de ataque promissora.

### 2. Detecção da injeção
- Teste de payloads clássicos no campo de usuário/senha para observar o comportamento da resposta.
- Confirmação de que a aplicação concatenava a entrada diretamente na query — sinal de **SQL Injection**.

### 3. Exploração
- Uso de **sqlmap** para confirmar e automatizar a extração, identificando o backend **SQLite**.
- Enumeração de tabelas e colunas do banco.

### 4. Análise do dump e escalada
- Análise dos dados extraídos para localizar o registro de um usuário com privilégios elevados.
- Uso dessa informação para escalar o acesso dentro da aplicação.

## 🧠 Aprendizados

- A diferença entre **detectar** a injeção manualmente e **automatizar** a extração com ferramenta.
- Reconhecer o SGBD pelo comportamento (sintaxe, mensagens, funções) muda a estratégia do ataque.
- O dump só vale quando se sabe **o que procurar** nele — a escalada veio da leitura cuidadosa dos dados.

## 🛡️ Como se defende

- Usar **prepared statements / queries parametrizadas**.
- Princípio do menor privilégio no usuário do banco.
- Nunca armazenar senhas em texto claro.
