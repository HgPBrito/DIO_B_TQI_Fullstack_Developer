# Comandos básicos

## GUI X CLI
O Git em base ele não tem interface gráfica, ele é um CLI (Command line interface) e não GUI (Graphical user interface), mas nos dias de hoje tem uma interface, mas o mais usado é por linha de comando.

## Comandos para navegação
### Comandos Windows essenciais
~~~cmd
dir          - traz a lista de pastas e arquivos contidos no diretório atual.
cd           - navega para o diretório passado cd caminho/da/pasta/requerida.
cls          - limpa o terminal
mkdir        - cria uma pasta
echo         - printa de volta no terminal, com o > nome_do_arquivo.tipo ele seta dentro do arquivo, caso não exista ele cria o arquivo.
del          - deleta somente arquivos
rmdir        - remove diretorio com todo conteúdo utilizando duas flags /S /Q
~~~
### Comandos Linux / MacOS essenciais
~~~bash
ls           - traz a lista de pastas e arquivos contidos no diretório  atual e usamos ls -a para mostrar aquivos ocultos.
cd           - navega para o diretório passado cd caminho/da/pasta/requerida.
clear        - limpa o terminal, também podendo usar CTRL + L
mkdir        - cria uma pasta
echo         - printa de volta no terminal, com o > nome_do_arquivo.tipo ele seta dentro do arquivo, caso não exista ele cria o arquivo.
rm           - remove o arquivo ou diretório passado, e para o diretório usa a flag -rf antes de passar o diretório (rm -rf ./diretorio/a/ser/removido)
~~~~

## Git por baixo dos panos

### Incriptação
Ele usa o SHA1 (Secure Hash Algorithm - Algoritmo de Hash Seguro), é um conjunto de funções hash criptográficas para a segurança de dados, projetada pela NSA (Agência de Segurança Nacional dos EUA).

### Objetos Git e suas funcionalidades básicas

* BLOBS

    Ele contém metadados do git dentro dele, contém o tipo do objeto, o tamanho do arquivo  uma \0 e o conteudo do arquivo.

* TREES

    Ela contém metadados mas agora contém, blobs ou outras trees e o nome do arquivo com sua extensão.

* COMMITS

    Ele é o objeto que junta tudo, ele aponta para uma tree, para um parente um commit anterior, o autor, uma mensagem e a hora criada. 

## Comandos do Git

* git init

    Inicia um repositório git no diretório atual.

* git config --global user.email "seu@email.com"

    configuração inicial que deve ser feita pela primeira vez no git, como um commit precisa de um autor, precisa ser passado o email do mesmo. Use --unset depois do global para limpar o campo.

* git config --global user.name "Seu Apelido"

    configuração inicial que deve ser feita pela primeira vez no git, como um commit precisa de um autor, precisa ser passaado o nome do mesmo. Use --unset depois do global para limpar o campo.

* git config --list

    lista toda configuração feita no git.

* git clone URL/do/repositorio/remoto

    Literalmente clona o repositório remoto para o diretório atual criando um repositório local apontando para o remoto clonado.

* git add *

    Ele prepara seus arquivos para o commt no caso do * são todos arquivos do diretório.

* git commit -m "mensagem de descrição"

    cria o commit com a mensagem de descrição.

* git status

    informa a situação dos arquivos no seu repositório.

* git remote add origin link

    adiciona um repositório remoto ao repositório local.

* git push origin branch

    envia os commits do repositório local para o repositório remoto.

## Criando um Arquivo Markdown

Todo arquivo Markdown tem a extensão em .md, e podemos usar o programa Typora para edição e visualização do arquivo.

### Títulos
~~~markdown
# Título1
## Título2
### Título3
#### Título4
##### Título5
###### Título6
~~~
> # Título1
> ## Título2
> ### Título3
> #### Título4
> ##### Título5
> ###### Título6

### Listas não ordenadas
~~~markdown
- item1
- item2
- item3
- item4
~~~

> - item1
> - item2
> - item3
> - item4

### Listas ordenadas
~~~markdown
1. item1
2. item2
3. item3
4. item4
~~~

> 1. item1
> 2. item2
> 3. item3
> 4. item4

## Resolvendo conflitos

### Conflito de merge

 Ele é causado quando a versão dos arquivos do repositório remoto está mais atualizado do que a versão dos arquivos do repositório local, com modificações nas mesmas linhas.

    git pull origin branch

É usado este comando para atualizar o local pelo remoto, mas precisa ser feito uma análise das linhas manualmente onde é separado pelos comentários de HEAD, depois de resolvido as diferenças, precisa commitar novamente e subir para o remoto.