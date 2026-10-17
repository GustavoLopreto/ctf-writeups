# CTF Writeups

> *Capture The Flag writeups focused on methodology and reasoning — not ready-made solutions.*

Coletânea de **writeups de CTF** resolvidos durante o curso de Segurança Cibernética. O objetivo destes documentos é registrar a **metodologia, as ferramentas e o raciocínio** por trás de cada desafio.

## 🔒 Política de sanitização

Todos os writeups seguem as mesmas regras:
- ❌ **Nenhuma flag** real é publicada.
- ❌ **Nenhum IP, porta ou endereço** de laboratório — substituídos por `<alvo do laboratório>`.
- ❌ **Nenhuma credencial** obtida em dumps.
- ✅ Foco em **técnica e aprendizado**, não na solução pronta.

## 📝 Writeups

| Desafio | Tema | Técnicas |
|---|---|---|
| [Copa 2026](writeups/copa-2026-sqli.md) | Web / SQL Injection | recon → SQLi no login → análise de dump → escalada |
| [Painel de Controle (Secure Bank)](writeups/secure-bank-auth-bypass.md) | Web / Auth Bypass | bypass de autenticação via SQL Injection |
| [Hash Collision](writeups/hash-collision-md5.md) | Cripto | reconhecimento de hash + colisão parcial de MD5 |

## 🛠️ Ferramentas recorrentes

`nmap` · `sqlmap` · `Burp Suite` · `SQLite` · utilitários de hash · análise manual
