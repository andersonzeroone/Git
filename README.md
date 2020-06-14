# Git


* [Para que serve o Git?](#Para-que-serve-o-Git?);   
* [instalação](#Instalação);
* [Configurando o  user](#Configurando-o-user);
* [Inicialização criando um novo repositório](#Inicialização-criando-um-novo-repositório);
* [Monitorando arquivos](#Monitorando-arquivos);
* [Historico de alterações](#Historico-de-alterações); 
* [Git ignore](#Git-ignore); 
* [](#); 
* [](#); 
* [](#); 
* [](#); 
* [](#); 
* [](#); 
* [](#); 
* [](#); 
* [](#); 
* [](#); 
* [](#); 
* [](#); 
* [](#); 

### Para que serve o Git?

É comum que quando se trabalho com desenvolvimento, trabalhar com mais de uma pessoa no mesmo projeto. E com isso cada pessoa tem o projeto em sua maquina e as mesmas faram alterações ao logo do desenvolvimento. Quando uma  pessoa faz uma alteração no projeto as outras precisam ser notificadas sobre  o enviou dessas alterações por meios físicos como pendrives, HD externo não seria muito interessante até por que no momento da entrega de uma alteração outra já poderia ter sido feita. Essa situação séria um pouco confuso e poderia trazer alguns problemas durante o desenvolvimento, por isso existi algumas soluções e uma dela é a criação de um servidor específico para o envio das alterações dos arquivos. Todos da equipe terão acesso a este servidor.
O servidor precisa ter alguma ferramenta capaz de identificar que a versão enviada não é a mais recente e não permitir o envio do projeto sem antes o usuário baixar a atual versão do projeto já que antes do envio das suas alterações ocorreram uma ou mais alterações no projeto. Isso é chamado de controle de versão. E é isso que o GIT faz, mas existem outros sistemas de controle de versão como:

* CVS
* SVN
* Mercurial
* GIT


O Git é o mais utilizado por conta de  algumas características vantajosas, como permitir uma cópia do projeto, um repositório do projeto em sua máquina, para que se possa trabalhar em cima dela e então enviá-lo para outro repositório, o que se denomina repositórios distribuídos.

## Instalação 

Para instalar basta acessar o [site oficial](https://git-scm.com/downloads)

```css
Caso você esteja utilizando Linux, algumas distribuições já vêm com o Git instalado, então é só abrir o Terminal e digitar "git  --version" para verificar isto. Se ele não estiver instalado, use  o gerenciador de pacotes da sua distribuição.
```

Feito o download, executaremos o arquivo, e durante a instalação, existem algumas opções  como o "Git Bash" , que é uma forma de digitar comandos. O Git Bash fornece comandos com os quais quem desenvolve em Linux já está acostumado a usar, como o ls para mostrar arquivos e pastas existentes no diretório atual.

A instalação padrão e clicando em "Next". Em "Adjusting your PATH environment", é possível definir se iremos usar apenas o Git Bash, ou então o Git de qualquer outra interface de linha de comando podem deixar padrão caso queira outra opção basta ler atentamente as opções.

Finalizada a instalação, podem desmarcar o box de "View Release Notes" e marcar "Launch Git Bash", para que se inicie a execução do Git Bash.
para garantir que tudo ocorreu bem no terminal digiti git --version, ao que será retornado git e a versão instalada.

## Configurando o  user 
Antes de utilizar o git precisa informa quem é o usuario para que ele possa salvar os dados do autor das alterações.

```css

git config --local user.name "Seu nome aqui"
git config --local user.email "seu@email.aqui"


```
É possivel configurar um email e autoria para cada projeto ou para a maquina toda atraves do comando:

```css

    //configurando para o projeto
    config --local  user.name "seu nome"
    config --local  user.email "seu email"

    // para a maquina toda
    git config --global user.name "seu nome"
    config --local  user.email "seu email"
```


## Inicialização criando um novo repositório.

Para inicializar o repositorio é preciso criar uma pasta com ou sem um projeto e executar o seguinte comando:

```css
 //comando
  git init.
```

img 01

Todas as alterações que forem realizadas no arquivo localizado dentro deste repositório poderão ser mostradas pelo Git  com algumas informações como,indicações do que foi modificado, quem modificou e outras.No final após criar será adcionadado o do Git Bash ((master)).

### Comando Status

Para verificar  o estado do repositório, ou analisar quais arquivos foram alterados use o comando git status.

```css
 //comando
  git status.
```
img 02

na mensagem será exibido algumas informações como, Untracked files, indica que há arquivos não monitorados no projeto, são arquivos que ainda não foram adicionados para o envio de uma nova atualização "commitar". para adcicionar esse arquivo é preciso utlizar o comando, git add nomeDoArquivo.

Ao executar o comando git status obetmos algumas informações como,HEAD, working tree e index e cada uma delas possui um definição.

HEAD: Estado atual do código.
working tree: Local onde os arquivos estão sendo armazenados e editados.
index: Local onde o Git armazena o que será commitado.

## Monitorando arquivos

Caso haja arquivos que nunca foi editado e salvo pelo Git, basta utilizar o comando:

```css

    git add nomeDoArquivo

    //se caso houver mais de um arquivo use 

     it add .

    // com o ponto no final

```


Com isso, se rodar o git status,  irá aparecer um retorno , incluindo Changes to committed, isto é, "mudanças a serem commitadas", ou salvas, enviadas.

Para salvar as modificações é preciso rodar comando git commit porém precisamos informa uma descrição de qual modificaç~ao estamos fazendo para isso é preciso incluir o -m no final do comando mais a mensagem.

```css
    git commit -m " mesagem de descrição"
    // a mensagem precisa está entre aspas duplas e ser a mensagem deve ser descritiva e curta
```

img 04

Após executar o comando será exibido  a mensagem que configuramos e será mostrado quais foram as alterações.Se executarmos git status novamente irá mostrar que não há nada para ser commitado.

Os commites devem serem feitos quando houver alterações significativas ou algum ponto que vocẽ quer lembrar. Não é recomendado executar commit quando algo no codigo não funciona,algumas pessoas defem o uso do commit apesar no final do expediente outras dizem que devem ser feitos  a cada alteração, não existi uma regra, e sim recomendações. 

## Historico de alterações 


Poderemos verificar o histórico de alterações, cada mensagem de commits feitos, o comando que poderemos utilizar para isto é git log, que nos mostrará diversas informações, sendo o primeiro deles um hash do commit, uma identificação única de cada commit,não existem dois commits com o mesmo hash.
A informação seguinte refere se ao  branch, ou "ramo" em que o commit se encontra. O HEAD e master quer dizer que é o local onde nos encontramos, no código, onde acontecem as alterações que fizermos, e que estamos em um ramo denominado master. Além de informações da autoria do commit, e-mail configurado, data do commit e mensagem.

05


O comando git log possue algumas variações:

    * git log --oneline: exibir as informações  por linhas;
    * git log -p: exibir mais informações.

Para filtros em log cheatsheet há vários delas como:

    * git log --pretty="format:%H":  traz apenas o hash;
    * git log --pretty="format:%h %s":  traz o hash resumido seguido pela mensagem do commit.

É possivel pesonalizar o comando de diversas formas de acordo com suas necessidades, é possivel acessar mais opções usando o comando git log --help ou acessando [git log cheatsheet](https://devhints.io/git-log).

## Git ignore

Quando temos um arquivo no projeto que não desejamos fazer commit podemos ignorar através da criação de um arquivo chamado ".gitignore" dentro da pasta do projeto(o arquivo pode ser criado diretamente pela IDE).Todas as linhas que estiver dentro dele seram ignoramos pelo git durante o commit, exemplo.

Se quisermos ignorar um arquivo basta abrir o aquivo .gitinore e adicionar o nome do arquivo, se for pasta adicionar o nome da com uma barra no final.

06





















Fonte:
 https://git-scm.com/docs/git-init;
 https://git-scm.com/book/pt-br/v2;
 https://rogerdudler.github.io/git-guide/index.pt_BR.html;