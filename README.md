
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

### **Git, Git Hub e as suas possibilidades com versionamento de código**

- #### Instalar e configurar o Git em uma máquina
    - Comandos para armazenar em diferentes locais como global, local e system, alterar nome de usuario e email, definir branch padrão
        - *git config --global*
        - *git config --global user.name seu-nome*
        - *git config --global user.email seu-email*
    - Definindo branch padrão
        - *git config init.defaultBranch main*
    - Mostrando as configurações globais
        - *git config --global --list*
- #### Autenticação via Token
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
- #### Criando e clonando repositórios
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
- #### Salvando alterações no repositório local
    - Entre na pasta do repositório Git
    - Cheque o status da arvore de trabalho:
        - *git status*     
    - Ao fazer modificações, após checar os status, o sistema informará que tem arquivos não commitados