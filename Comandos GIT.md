# Guia de referência com os principais comandos GIT
Exemplos dos principais comandos utilizados para gerenciar um repositório GIT. Estes comandos funcionam em ambientes Linux e Mac utilizando o terminal ou em ambiente Windows com o Git Bash ou Powershell.

**Autor:** Guilherme Moreira de Castro (guilherme@datalinux.com.br)

## Como clonar um repositório GIT?

```git clone XXXXXX```

Onde XXXXXX é o endereço do repositório GIT. Se for um repositório público, os dados serão clonados. Se o repositório for privado e a comunicação for via HTTPS provavelmente será solicitado a senha. Se for via SSH será necessário ter a chave pública da sua máquina cadastrada no serviço de hospedagem do repositório

## Como criar um repositório GIT?

```git init```

Acesse a pasta onde estão os arquivos e digite o comando acima, desta forma um repositório será inicializado


## Como adicionar arquivos em um repositório?

```git add *```

Acesse a pasta e digite o comando acima. Isso irá adicionar ao controle do repositório todos os arquivos da pasta. Se desejar adicionar apenas um arquivo ou pasta, basta trocar o * pelo nome do arquivo ou caminho da pasta. Se for necessário forçar a inclusão de algum arquivo ou pasta, adicionar a opção -f

## Como realizar um commit?

```git commit -a```

O commit serve para salvar todos os arquivos do repositório no seu estado atual, criando uma marca na linha do tempo do repositório. Acesse a pasta do repositório e digite o comando acima. Um editor de texto no próprio terminado será acionado e uma mensagem sobre o commit poderá ser escrita. Importante entender qual é o editor de texto *command-line* que seu computador possui para salvar as mensagens. Se a mensagem for curta pode ser digitada direto no comando utilizando ```git commit -m "Mensagem do commit"```

## Como criar uma nova branch

```git branch XXXXX```

Troque o XXXXX pelo nome da branch. A branch é como se fosse uma imagem do seu repositório no estado atual, mas é independente. Ou seja, criando uma nova branch o conteúdo dela ficará intacto se as outras branches forem alteradas. Isso é utilizado muito quando desenvolvedores diferentes atuam sobre o mesmo código e cada um irá realizar uma alteração apenas em parte do código. Esse comando deve ser digitado dentro da pasta do repositório. Se desejar listar todas as branches digite apenas ```git branch```

## Como acessar um branch?

```git checkout XXXXX```

Dentro da pasta do repositório digite o comando e a branch será carregada. Todo o conteúdo da pasta do seu repositório será alterado para o conteúdo da branch escolhida. Para evitar confusões, antes de fazer o checkout para uma outra branch, salve o estado atual do repositório em um commit ou descarte as alterações. É possível criar uma nova branch e já trocar para ela usando ```git checkout -b XXXXX``` onde XXXXX é o nome da nova branch

## Como voltar o estado dos seus arquivos para as alterações para do último commit?

```git reset --hard HEAD~1```

Fazendo isso dentro da pasta do repositório, serão descartadas todas as alterações feitas nos arquivos e o último commit será restaurado. É possível voltar as alterações de qualquer commit anterior ou apenas de um arquivo com o comando ```git reset --hard XXXXX``` onde XXXXX é o hash do commit que deseja restaurar ou o nome do arquivo.

## Como mesclar duas branches?

```git merge XXXXX```

Acesse a pasta do seu repositório, e faça o checkout para a branch que irá receber as alterações (branch destino). O XXXXX é o nome da branch origem que irá mesclar com a branch atual.

## Como adicionar um repositório remoto?

```git remote add origin XXXXX```

Faça isso dentro da pasta do seu repositório. Isso irá adicionar um repositório remoto com o nome padrão origin e o XXXXX é o endereço do seu repositório remoto.

## Como enviar as alterações ao repositório remoto?

```git push XXXXX YYYYY```

Faça isso dentro do seu repositório e troque o XXXXX pelo nome do repositório remoto (geralmente origin) e o YYYYY pelo nome da branch que você deseja enviar (geralmente master). Se for necessário forçar o envio para sobrescrever o repositório remoto com sua versão atual utilize ```git push -f XXXXX YYYYY```. Se desejar enviar as tags use o comando ```git push -f XXXXX YYYYY --tags```

## Como receber as alterações do repositório remoto em meu repositório local?

```git pull XXXXX YYYYY```

Faça isso dentro do seu repositório local e com um repositório remoto configurado. O conteúdo do repositório remoto será importado ao seu repositório local. Este pode ser um dos procedimentos para atualizar seu código do ambiente de produção com a última versão. Se for necessário forçar o recebimento para sobrescrever o repositório local com a sua versão remota utilize ```git pull -f XXXXX YYYYY```. Se desejar receber as tags use o comando ```git pull -f XXXXX YYYYY --tags```

## Como tagear o meu repositório?

```git tag XXXXX```

Faça isso dentro da pasta do seu repositório e substitua XXXXX pelo valor da sua tag. A tag serve para criar um nome e marcar na linha do tempo uma versão do seu código. Pode-se usar como valor de tag, por exemplo, o sistema de versionamento semântico (0.1.0, 0.2.0, 1.2.0, etc). Se desejar visualizar todas as tags do seu repositório, utilize o comando ```git tag -l```