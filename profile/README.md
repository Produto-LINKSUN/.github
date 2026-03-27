# 📘 Manual de Padrões e Boas Práticas de Uso do Git

Este documento define os padrões obrigatórios para uso do Git no projeto.  
O objetivo é garantir:

- 🔐 Segurança  
- 🧹 Organização  
- 🔍 Rastreabilidade  
- ♻️ Sustentabilidade  
- 📏 Padronização  

---

## 🎯 Objetivos

- Evitar vazamento de informações sensíveis  
- Manter o repositório limpo e leve  
- Garantir histórico de commits útil  
- Facilitar revisão de código e deploy  
- Padronizar o trabalho entre desenvolvedores  

---

## ❌ O que NÃO deve ser commitado

### 1️⃣ Testes rápidos e arquivos temporários

Não commitar:

- Arquivos de teste local (ex: `teste.js`, `debug.py`)
- Rascunhos (`rascunho.txt`)
- Scripts sem uso real

✔️ Se for um teste válido:
- Deve estar em `tests/` ou similar  
- Deve ter nome claro  
- Deve fazer parte do projeto  

---

### 2️⃣ Arquivos `.env` e credenciais

🚫 Nunca commitar:

- `.env`
- `.env.*`
- Qualquer credencial real

⚠️ Risco: vazamento de dados e acesso indevido

✔️ Padrão correto:

```env
# .env.example
DB_HOST=
DB_USER=
DB_PASSWORD=
DB_NAME=
```

✔️ O `.env` real deve estar no `.gitignore`

---

### 3️⃣ Banco de dados e dumps

🚫 Não versionar:

- `.sql`
- Backups
- Dados reais

📌 Git não é ferramenta de backup

✔️ Use:
- Migrations  
- Scripts de estrutura  
- Seeders  

---

### 4️⃣ Backups e arquivos compactados

🚫 Não commitar:

- `backup/`, `dump/`, `old/`
- `.zip`, `.tar`, `.tar.gz`

📌 Motivo:
- Polui o repositório  
- Aumenta tamanho desnecessariamente  

---

### 5️⃣ Dependências e builds

🚫 Nunca commitar:

- `node_modules/`

🚫 Também evitar:

dist/
build/
.out/
.next/
coverage/

✔️ Esses arquivos são gerados automaticamente

---

### 6️⃣ Logs e cache

🚫 Não versionar:

*.log
logs/
.cache/
.tmp/

---

## 📁 Uso correto do `.gitignore`

Todo projeto deve ter um `.gitignore` bem definido:

```gitignore
# Ambiente
.env
.env.*

# Node
node_modules/
npm-debug.log*
yarn-error.log*

# Build
dist/
build/
coverage/

# Logs
*.log
logs/

# Banco / backups
*.sql
backup/
dump/

# SO / IDE
.DS_Store
.vscode/
.idea/
```

📌 O `.gitignore` é obrigatório

---

## 🧠 Responsabilidade do Desenvolvedor

Antes de commitar, pergunte:

> “Esse arquivo é necessário para outra pessoa rodar ou entender o sistema?”

Se a resposta for **não**, não deve ser commitado.

---

## 🤖 Automação e Proteção

✔️ **Pre-commit (local)**  
Evita erros antes do commit  

✔️ **CI (GitHub Actions)**  
Valida código automaticamente  

✔️ **Proteção de branch**  
- `main` e `develop` protegidas  
- Merge apenas via Pull Request  

---

## ✅ Checklist antes do commit

- [ ] Não inclui `.env` ou credenciais  
- [ ] Não inclui `node_modules`  
- [ ] Não inclui dumps ou backups  
- [ ] Não inclui arquivos temporários  
- [ ] Arquivos têm propósito claro  
- [ ] `.gitignore` está sendo respeitado  

---

## 🧾 Conclusão

Git não é só versionamento — é:

- Controle  
- Segurança  
- Qualidade  

Seguir estes padrões:

- Evita problemas em produção  
- Mantém o projeto saudável  
- Facilitação crescimento do time  
- Reduz retrabalho  

---

## 🔗 Manual completo (versão visual)

👉 [coloque aqui o link do GitHub Pages]
