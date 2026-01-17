# 🐙 Guia Mestre: Git & GitHub

Este repositório é um manual prático e definitivo para o controle de versão. Aqui você encontrará tudo o que precisa para configurar, gerenciar e manter seus projetos de forma profissional e segura.

---

## 🚀 1. Configuração Inicial (Primeiro Upload)
Siga esta ordem exata ao iniciar um novo projeto para garantir que o repositório comece limpo e sem arquivos desnecessários.

1.  **Iniciar o repositório local:**
    ```bash
    git init
    ```
2.  **Configurar o Filtro de Arquivos (.gitignore):**
    *Crie o arquivo antes de qualquer outro comando para evitar o upload de pastas pesadas.*
    ```bash
    echo "node_modules/" > .gitignore
    ```
3.  **Preparar e Salvar a primeira versão:**
    ```bash
    git add .
    git commit -m "feat: setup inicial do projeto"
    ```
4.  **Conectar ao GitHub:**
    ```bash
    git branch -M main
    git remote add origin URL_DO_SEU_REPOSITORIO
    git push -u origin main
    ```

---

## 🔄 2. O Ciclo Diário (Os 6 Comandos Principais)
Estes comandos representam a rotina de um desenvolvedor e devem ser usados constantemente.

| Comando | Descrição |
| :--- | :--- |
| **`git pull origin main`** | **Sempre use primeiro.** Sincroniza seu código com as novidades do servidor. |
| **`git status`** | Verifica quais arquivos foram alterados ou criados desde o último commit. |
| **`git add .`** | Prepara todas as suas mudanças para serem "empacotadas". |
| **`git commit -m "..."`** | Cria uma nova versão oficial do código com uma etiqueta descritiva. |
| **`git push origin main`** | Envia suas versões salvas localmente para o repositório no GitHub. |
| **`git log --oneline`** | Mostra o histórico resumido de todas as versões criadas. |

---

## 🔑 3. Autenticação: Personal Access Token (PAT)
Por segurança, o GitHub exige um **Token de Acesso** no lugar da sua senha comum no terminal.

### Como gerar:
1.  No GitHub: Vá em **Settings** > **Developer Settings** > **Personal access tokens** > **Tokens (classic)**.
2.  Clique em **Generate new token (classic)**.
3.  Dê um nome (ex: "IDX-Master") e marque a permissão **`repo`**.
4.  Gere o token e **copie o código imediatamente**. (Ele não aparecerá novamente).

### Como usar:
* **Username:** Seu nome de usuário do GitHub.
* **Password:** Cole o **Token** gerado. (O cursor não se move por segurança, apenas cole e dê Enter).

---

## 🛡️ 4. A Importância do .gitignore
O `.gitignore` é o seu escudo contra arquivos desnecessários. Ele mantém o repositório leve e protege seus dados sensíveis.

**O que deve ser ignorado:**
* `node_modules/`: Bibliotecas que podem ser reinstaladas via `npm install`.
* `.env`: Arquivos que contêm senhas e chaves secretas de API.
* `npm-debug.log*`: Arquivos temporários gerados em caso de erro.

---

## 🆘 5. Comandos de Emergência (O "Ctrl+Z" do Git)
Fez algo errado? Use estes comandos para recuperar seu trabalho:

* **Desfazer mudanças não salvas em um arquivo:** `git checkout -- nome-do-arquivo`
* **Remover algo do Git sem apagar da sua pasta real:** `git rm --cached nome-do-arquivo`
* **Desfazer o último commit (mas manter o código escrito):** `git reset --soft HEAD~1`

---

## 📝 6. Boas Práticas: Commits Semânticos
Para um histórico profissional e fácil de ler, utilize estes prefixos em suas mensagens:

* **`feat:`** Adição de uma nova funcionalidade.
    * *Ex: `git commit -m "feat: adiciona sistema de busca"`*
* **`fix:`** Correção de algum erro ou bug.
    * *Ex: `git commit -m "fix: corrige alinhamento do botão"`*
* **`docs:`** Mudanças apenas em documentações (como este README).
    * *Ex: `git commit -m "docs: atualiza guia de git"`*
* **`style:`** Formatação, pontos e vírgulas, espaços (não altera a lógica).
* **`chore:`** Atualizações de tarefas de rotina ou bibliotecas.
    * *Ex: `git commit -m "chore: atualiza dependências do express"`*

---
