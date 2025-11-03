# Guia Essencial de Git e GitHub (Resumo do Curso)

Este guia consolida os comandos e conceitos essenciais de Git e GitHub aprendidos no curso da Alura.

---

## 1. Configuração e Inicialização

| Tópico | Comandos e Conceitos |
| :--- | :--- |
| **Instalação e Conta** | Criar conta no GitHub. Baixar e instalar o Git no computador. |
| **Identidade do Autor** | Configurar o nome e e-mail que aparecem nos commits: `git config --global user.name` e `git config --global user.email`. |
| **Criação de Repositórios** | **Remoto:** Criar um repositório no site do GitHub. **Local:** Iniciar o Git na sua pasta de projeto com `git init`. |

---

## 2. Fluxo de Trabalho Básico e Salvamento

Este é o ciclo padrão para registrar e enviar alterações.

| Comando | Função / O que faz |
| :--- | :--- |
| `git status` | Visualizar quais arquivos foram modificados (ver o "estado" do repositório). |
| `git add <arquivo>` ou `git add .` | Realizar alterações e registrá-las como *commits* no histórico local. |
| `git commit -m "Mensagem"` | Salvar as alterações preparadas (`git add`) no histórico **local**. |
| `git log` | Listar o histórico de *commits* (ID, autor, data e mensagem). |
| `git clone [URL]` | Baixar uma cópia do repositório remoto para o computador (cria o repositório local e a conexão de uma vez). |

---

## 3. Comunicação Local e Remota (GitHub)

| Comando | Protocolo | Propósito |
| :--- | :--- | :--- |
| `git remote add origin [URL]` | --- | Cria um atalho (`origin`) para o endereço do repositório no GitHub. |
| `git push origin main` | Envio | Enviar *commits* locais para o repositório remoto (GitHub). |
| `git pull origin main` | Recebimento | Baixar *commits* do remoto para o local (faz `fetch` + `merge`). |
| `git remote -v` | --- | Visualizar os repositórios remotos linkados (URLs de *fetch* e *push*). |

---

## 4. Máquina do Tempo e Desfazimento

| Comando | Propósito | Uso Comum |
| :--- | :--- | :--- |
| `git revert [HASH]` | Desfazer o efeito de um *commit* específico, criando um **novo *commit*** de desfazimento. **(Recomendado para histórico público)** |
| `git reset --hard [HASH]` | Apagar *commits* do histórico **local** e descartar as alterações no código. **(Recomendado para histórico privado)** |
| `git commit --amend` | Modificar a mensagem ou o conteúdo do **último *commit*** realizado. |
| `git reset --hard HEAD~N` | Desfazer os últimos *N* *commits* (ex: `HEAD~1` desfaz o último). |

---

## 5. Conflitos e Boas Práticas

* **Conflitos:** O Git sinaliza conflitos com marcações visuais (`<<<<<<<`, `=======`, `>>>>>>>`).
* **Resolução de Conflitos:** Após editar o arquivo manualmente e remover as marcações, é OBRIGATÓRIO usar **`git add .`** seguido de **`git commit`** para registrar a resolução.
* **Integração VSCode:** Utilizar o Git pela interface visual do VSCode é uma alternativa ao terminal.
* **Documentação:** Criar o arquivo `README.md` para documentar o projeto.
* **Ignorando Arquivos:** Criar o arquivo oculto **`.gitignore`** para que o Git ignore arquivos temporários ou de sistema.