# CTF Hash Collision — Colisão Parcial de MD5

**Categoria:** Criptografia · **Técnicas:** reconhecimento de hash, colisão parcial de MD5

> ⚠️ Writeup sanitizado: sem flag e sem IP. Foco na metodologia.

## 🎯 Desafio

Desafio de criptografia envolvendo um hash **MD5** e a necessidade de reconhecê-lo / explorar a fragilidade do algoritmo.

## 🧭 Metodologia

### 1. Reconhecimento do hash
- Identificação do formato: 32 caracteres hexadecimais → candidato a **MD5**.
- Verificação se era um hash **conhecido** (string comum já catalogada), antes de partir para força bruta.

### 2. Por que MD5 é frágil
- MD5 é vulnerável a **colisões**: entradas diferentes que produzem o mesmo digest.
- O desafio explorava justamente o reconhecimento dessa fragilidade, não a quebra criptográfica completa.

### 3. Resolução
- Reconhecimento do hash conhecido / aplicação do conceito de **colisão parcial** para atender à condição do desafio.

## 🧠 Aprendizados

- Antes de "quebrar" um hash, vale checar se ele é **conhecido** — economiza muito tempo.
- MD5 **não serve** para segurança: colisões são demonstráveis e práticas.
- Diferença entre **reverter** um hash (impossível por definição) e **encontrar uma colisão**.

## 🛡️ Como se defende

- Nunca usar MD5 (nem SHA-1) para integridade de segurança ou senhas.
- Para senhas: `bcrypt`, `scrypt` ou `Argon2` com salt.
- Para integridade: família **SHA-2 / SHA-3**.
