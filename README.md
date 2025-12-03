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

### Stage

Ao adicionar seu trabalho no **stage** ele vai para um lugar espécial no git. Aqui ele já está sendo rasteadro e versionado, as mudanças aqui são salvas e podemos dá nomes a essas alterações, mas ela não está de fato "salva" no repositório do git. Para registrar esse evento no repositório é preciso 'confirma' essas alterações, ao confirmar criamos um histórico de mudanças. Ao confirma dando uma descrição ela será levada para o repositório git,
a mudança recente recebe um **HEAD**, a cabeça do repositório o inicío de outras versões do mesmo arquivo.

Não lembro se já citei, mas para adicionar arquivos para o **stage** é necessário usar o commando `git add <nome do arquivo>` ou para adicionar todas pastas de um diretório use o comando `git add .`. Ou para adicionar todas as alterações do **working directory** use o parâmetro `-A`: `git add -A`. Ainda dá para mover por seleção: `git add *.txt` todos arquivos e textos serão movidos para o **stage**.

Vale ressaltar que os arquivos "validos" quando versionados são os que estão no ambiente git. O que significa que as alterações no **working directory** não são "originais" até que você adicione elas ao **storage** e posteriomente ao **git repository**. O que significa que qualquer alteração no working directory, você pode voltar a versão original ou uma versão qualquer usando alguns commandos. O git `git restore <file name>`, volta ao estado original do código que está no **storage**.

### Repositório git

Aqui é quando o trabalho chega ao "fim" ou um estágio aceitável. Nesse local que os arquivos são salvos permanentimentes, códigos finalizados e prontos para a produção.

## diferenças do stage e o working directory

Usando o comando `git diff <nome do arquivo>`

![Imagem demostrando o diff](https://res.cloudinary.com/dyvfesbzn/image/upload/v1764770892/diff_whcfau.png)

Com ela é possível ver o que foi adicionado ou removido no working directory.

## Confirmando as alterações no working directory

Estamos modificando e trabalhando em nosso working directory, mas cheguei em um nível aceitavel, adicionei eles ao stage e agora quero confirma essas mudanças e versionar elas, como confirmo elas?

Aprendemos a mové-las do working directory para o stage, mas como confirmamos as alterações do stage e mandamos elas para git repository?

Para isso é necessário nomeiar e até mesmo descrever essas alterações, para isso usamos o comando `git commit`. Com ele podemos rastreiar quem fez mudanças, evitar a sobreescrita dos códigos que é fundamental para trabalhar em equipe.

### commit

Vamos então fazer nosso commit! Vamos mandar as alterações do arquivo `newFile.txt` para o git repository:

`git commit -m "Title: Adicionando novo texto ao newFile.txt" -m "Description: um texto que representa uma alteração que não está no stage e que agora está de fato sendo rastreada pelo git, pois usamos o commando git add para adicionar ao stage."`

Meu Deus! Que trem GIGANTESCO!!! sim, de fato é enorme kkkk, mas não é obrigatorio escrever um commit desse tamanho. Vamos decompor as partes do comando commit:

`git commit` <- Diz que vamos confirmar mudanças para o git repository

`-m` <- é a abreviação de `-message`, é aquela **identificação** que temos que pôr nas mudanças, lembra? e por que você usou duas vezes o parâmetro `-m`? Basicamente quando usamos o `-m` pela primeira vez, escrevemos uma mensagem na primeira linha, ou seja, quando adiciono um segundo `-m` estou escrevendo na segunda linha do commit uma outra mensagem.

![commit changes](https://res.cloudinary.com/dyvfesbzn/image/upload/v1764771875/commitchanges_kozy2r.png)

Podemos agilizar o processo usando outro parâmetro no comando `commit`, o `-a` adicionar arquivos que não foram adicionados ao **stage** sem a necessidade de usar o comando `git add` toda vez que for fazer um commmit.

### Ajustando o último commit feito

Usando o commit `git commit --amend -m "ajustando o ultimo commit"` com isso você altera o último commit.

## Diferenças entre o último commit e o stage atual

Usando o comando `git diff --staged` você consegue comparar as mudanças atuais do **stage** que ainda não foi confirmado com o último commit no **git repository**

![Git diff entre staged e git repository](https://res.cloudinary.com/dyvfesbzn/image/upload/v1764773388/diffstaged_v8xsf6.png)
