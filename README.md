# Git

Git é um código livre e aberto Sistema de controle de versões distribuído projetado para lidar com tudo, desde pequenos até pequenos projetos muito grandes, com velocidade e eficiência.

## Configuraão básica do git

No mínimo deve-se configurar o nome de usuário e email, para isso basta usar os seguintes comandos:

### Configurando o nome de usuário

`git config --global user.name "<nome aqui>"`

### Configurando o email de usuário

`git config --global user.email "<email aqui>"`

O parâmetro `--global` apenas indica o escopo da configuração! No git temos dois escopos principais eles sendo: **local** e o **global**. O global é a conafiguração que vale para todos repositórios da máquina, já o local é exclusivo para um repositório em específico.

### Listando as configurações

Para exibir as informações de configuração use o comando:

`git config --global --list`

As mesma coisas sobre o parâmetro global, vale para o list.

## O que é um repositório?

Um repositório é um conjuto de arquivos e diretórios que são rastreados pelo git. Possibilitando versioná-las e refazer alterações!

### Iniciando um repositório

Para iniciar um basta escolher um diretório que deseja versionar e usar o comando `git init`,
irá criar um arquivo .git (invisivel), nele contém os arquivos que versiona seu diretório, geralmente não mexemos nele.

![imagem comandos criando um repositório](https://res.cloudinary.com/dyvfesbzn/image/upload/v1764687172/gitinit_azfifb.png)

## Clonando um repositório

Podemos clonar um repositório também! Para isso basta usar o comando:

`git clone [<url do git> / ou caminho do git]`

Assim você faz uma cópia do repositório! Lembrando que você pode facilmente clonar repositórios do próprio github.

## Fluxo do trabalho do git

Aqui vamos entrar em um tópico importante! É preciso saber e entender bem como o git trabalha e não é difícil, o git trabalha com dois estágios eles são **STAGE** e o **git repository**.

Quando iniciamos um repositório, possíveis arquivos existentes ou criados não são versionados automaticamente podendo você escolher se serão ou não versionados.

### Working directory

Aqui você está apenas modificando e trabalhando no diretório, arquivos criados, deletados ou modificado não são rastreados pelo git, a não ser que você adiciones ao seu "palco" onde o git consegue ver e versionar ele.

Você pode trabalhar aqui avontade! Modificar, deletar e criar arquivos. Fez algo que não gostou? pode voltar a versão anterior que foi "salva" pelo git etc...

## Stage

Ao adicionar seu trabalho no **stage** ele vai para um lugar espécial no git. Aqui ele já está sendo rasteadro e versionado, as mudanças aqui são salvas e podemos dá nomes a essas alterações, mas ela não está de fato "salva" no repositório do git. Para registrar esse evento no repositório é preciso 'confirma' essas alterações, ao confirmar criamos um histórico de mudanças. Ao confirma dando uma descrição ela será levada para o repositório git,
a mudança recente recebe um **HEAD**, a cabeça do repositório o inicío de outras versões do mesmo arquivo.

## Repositório git
