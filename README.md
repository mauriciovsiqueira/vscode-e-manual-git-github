## ⚙️ Configurações e extensões do VSCODE     
### Extensões:  
Portuguese (Brazil) Language Pack for Visual Studio Code  
prettier  
Live server  
Code runner  
Rainbow Brackets  


### Settings.json:
Para manter o editor formatado e leve, utilize estas configurações no seu VS Code:  
Atalho: crtl + shift + p   
Na caixa de pesquisa: open user settings (JSON)  
Substitua o que tem no JSON:


```bash
{
  "files.autoSave": "onFocusChange",
  "editor.formatOnSave": true,
  "editor.defaultFormatter": "esbenp.prettier-vscode",
  "explorer.confirmDelete": false,
  "git.autofetch": true,
  "git.enableSmartCommit": true,
  "git.confirmSync": false,
  "code-runner.saveAllFilesBeforeRun": true,
  "javascript.updateImportsOnFileMove.enabled": "always",
}
```

---

<br>

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
    *Obs.: Pode solicitar que coloque o email e o nome para proceder, coloque seu email e nome dentro das " ".*
    ```bash
    git config --global user.email "seu-email@exemplo.com"
    git config --global user.name "Seu Nome"
    ```
    **Rode o comando do passo 3 novamente!**
    
4.  **Conectar ao GitHub:**
    ```bash
    git branch -M main
    git remote add origin URL_DO_SEU_REPOSITORIO
    git push -u origin main
    ```
    *Obs.: Caso tenha arquivos no seu repositório irá dar erro, precisa primeiro atualizar com o comando pull.*
    ```bash
    git pull origin main --allow-unrelated-histories
    ```
    <br>  
    
    **Caso dê erro, prossiga com esses comandos:**    
    1. **Configure a estratégia de união:**
    Execute este comando para definir que você prefere o "merge" (unir as histórias):
     ```bash
    git config pull.rebase false
    ```

    2. **Tente o pull novamente:**
    Agora que a estratégia foi definida, repita o comando anterior:
    ```bash
    git pull origin main --allow-unrelated-histories
    ```

    *Atenção: Se o terminal abrir um editor de texto (como o Vim ou Nano) com uma mensagem de commit, apenas salve e saia. No Vim, digite :wq e dê Enter.* 

    **Envie seus arquivos!:**
    ```bash
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

## 🔧 Manutenção: Mudei o nome do repositório no GitHub
Se você alterou o nome do projeto no site, atualize o link local para não perder a conexão:
```bash
git remote set-url origin NOVA_URL_AQUI
```

Verficar se a conexão está certa:  
```bash
git remote -v
```

Para verificar se tem algo no repositório e puxar e depois enviar:
```bash
git pull origin main
git push origin main
```

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

## 📝 7. Para formatação do README.md:
Visite: https://docs.github.com/pt/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax

---
