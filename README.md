
# Curso Git e Git Hub

Repositório de estudos para versionamento de código com Git e Git Hub

- Obs.: Estudos e aplicações é para serem executados em ordem sequencial

## 📚 Documentação

- [Documentação Git](https://git-scm.com/doc)
- [Documentação Git Hub](https://docs.github.com/pt)
- [Documentação da linguagem de marcação Markdown para README](https://docs.github.com/pt/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/quickstart-for-writing-on-github)

## 💻 Conhecimentos aprofundados

| Assuntos | O que é? |
| ------------- | ------------- |
| Versionamento de código | Controlam as versões de um arquivo ao longo do tempo
| Git | Sistema de controle de versões
| Git Hub | Plataforma de hospedagem de código |

## 📖 Estudos e aplicações

### Versionamento de código e a sua importância

- Controlam as versões de um arquivo ao longo do tempo
- Registra o histórico de atualizações de um arquivo
- Gerencia quais foram as alterações, a data, autor, etc.;
- Organização, controle e segurança

- **Sistemas de controle de versão:**
    - **VCS Centralizado:**
        - Um servidor será responsável por todo o controle de versionamento
    - **VCS Distribuido:**
        - Cada banco de versão é duplicado localmente
        - Clona o repositório completo, o que inclui o histórico de versões
        - Cada clone é como um backup;
        - Possibilita um fluxo de trabalho flexível
        - Possibilidade de trabalhar sem conexão à rede

## ⚙️ **Git, Git Hub e as suas possibilidades com versionamento de código**

- ### Instalar e configurar o Git em uma máquina
    - Comandos para armazenar em diferentes locais como global, local e system, alterar nome de usuario e email, definir branch padrão
        - *git config --global*
        - *git config --global user.name seu-nome*
        - *git config --global user.email seu-email*
    - Definindo branch padrão
        - *git config init.defaultBranch main*
    - Mostrando as configurações globais
        - *git config --global --list*
- ### Autenticação via Token
    - [Criar](https://github.com/new) repositório no Git Hub e fazer as devidas configurações
        - Escolher se será privado ou público
        - Adicionar README.md
        - Pode selecionar .gitignore para ignorar arquivos da sua escolha
    - Gerar token no [Git Hub](https://github.com/settings/tokens)
        - Selecionar data de expiração e possíveis limitações de escopo
        - Copie o token, **cuidado** ⚠️, ao sair da página o não é possível visualizar mais o token 
    - Copiar URL do repositório em *<>code*
    - Comando para configurar o token ao clonar um repositório:
        - *git clone URL-aqui* ***Obs.: não vai clonar ainda***
        - Colocar usuário definido e colar o token gerado
    - Comando para visualizar o token dentro do Git:
        - *git config --global credential.helper store*
        - *git config --global --show-origin credential.helper*
        - *cat .git-credentials* (dentro da pasta onde está o .gitconfig)
- ### Criando e clonando repositórios
    - Diretório local:
        - Criar pasta dentro de uma pasta de sua preferência:
            - *mkdir nome-da-pasta*
        - Avançar na pasta
            - *cd nome-da-pasta*
        - Para iniciar repositório git    
            - *git init* 
        - Para conectar repositório local com remoto:
            - *git remote add origin link-repositorio*
        - Confirme se os repositórios estão conectados:
            - *cd .git*
            - *cat config*




    - Diretório remoto:
        - Dentro da pasta desejada execute esse comando:
            - *git clone URL-aqui* 
                - Para clonar e mudar o nome da pasta:
                    - *git clone URL-aqui nome-da-pasta-aqui*
        - Confirme se os repositórios estão conectados:
            - *git remote -v*
- ### Salvando alterações no repositório local
    - Entre na pasta do repositório Git
    - Cheque o status da arvore de trabalho:
        - *git status*     
    - Ao fazer modificações, após checar os status, o sistema informará que tem arquivos não commitados
    - Adicione arquivos para fila do commit:
        - *git add nome-do-arquivo*
    - Cheque o status:
        - *git status*
    - Faça o commit:
        - *git commit -m"nome do commit"*

    ```
    - Comando << touch nome-do-arquivo >> para adicionar arquivos

    - Comando << mkdir nome-da-pasta >> para adicionar pastas

    - Comando << echo nome-do-arquivo-ou-pasta > .gitignore >> para
    ignorar alterações na arvore de trabalho

        - Comando << echo > .gitignore >> para remover esses arquivos

    - Comando touch nome-do-diretorio/.gitkeep para reconhecer diretorios

    - Comando git add . para adicionar todos os arquivos a arvore de 
    trabalho
    ```

- ### Desfazendo alterações no repositório local
    - **Desfazendo todas as alterações que foram feitas diretamente no arquivo:**
        - Utilize o comando:
            - *git restore nome-do-arquivo*
        - Como alterar mensagem do último commmit
            - *git commit --amend -m"coloque sua mensagem aqui"
    - **Como desfazer commits anteriores:**
        - **Soft: Remove o commit inteiro**
            - Copie o hash do commit
                - *git log*
            - Após isso:
                - *git reset --soft hash-do-commit
            - Cheque se o commit foi resetado com o comando *git log*
        - **Mixed: Coloca o último commit na árvore de trabalho** 
            - Copie o hash do commit
                - *git log*
            - Após isso, use:
                - *git reset --mixed hash-do-commit*
            - Cheque se o commit foi resetado com o comando *git log*
        - **Hard: Elimina todas as mudanças não commitadas**
            - Copie o hash do commit
                - *git log*
            - Após isso, use:
                - *git reset --hard hash-do-commit*
            - Cheque se o commit foi resetado com o comando *git log*
    - Tirar arquivos da arvore de trabalho:
        - Ao adicionar arquivos a area de preparação com o comando *git add*, você também pode remove-los:
            - *git reset nome-do-arquivo* ou *git restore --staged nome-da-pasta/nome-do-arquivo*

- ### Enviando e baixando alterações com o repositorio remoto
    - **Enviando alterações para repositório remoto:**

        - Adicionar o link de origem do repositório:
            - *git remote add origin link-do-repositório*
        - Forçar branch para main:
            - *git branch -M main*
        - Envie para o repositorio e atualize seu Git Hub (finalmente)
            - *git push -u origin main*
    - **Como baixar as alterações do repositório remoto para o local**
        - Utilize o comando:
            - *git pull*
- ### Trabalhando com branches
    - Uma branch é uma ramificação do seu projeto
    - É um repositório móvel para um commit no histórico do repositório
    - Quando você cria uma nova branch a partir de outra existente, a nova se inicia apontando para o mesmo commit da branch que estava quando foi criada