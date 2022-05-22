# Git e Github

Projeto criado para instruir os alunos do programa devstart, quanto a utilizção do Git e Github. Utilizaremos este repositório para salvar dicas e comandos uteis do git e da plataforma Github.


## Autores

- [@AlexDeveloperOne](https://github.com/AlexDeveloperOne) Alexandre


## Funcionalidades



## configurando a identidade no git
- git config --global user.name = ‘seu nome’
- git config --global user.email = ‘seu@email’

## listando as configurações de identidade
- git config --list

## lista de comandos possíveis[dando acesso à documentação]
- git

## relembrando comandos comuns…
- git init [inicia a versionamento dentro do repositório onde o comando foi dado]
- git status [verifica o status atual do versionamento]
- git add aula1.txt [prepara o aula.txt para ser commitado]
- git add . [para todos]

## reverte o git add
- git rm --cached aula1.txt

## commita os arquivos adicionados (add)
- git commit -m 'Versao inicial'
- git push [enviar alterações do repositório local para o  repositório remoto]
- git pull [receber alterações do repositório remoto no repositório local]

## logs sobre commits [autor;data;mensagem]
- git log
- git log --oneline [outro método de visualização]

## list todas as branchs e a que estamos no momento
- git branch

## criação de branch
- git branch nome_da_branch

## saltar para outra branch
- git checkout nome_da_branch
  - ao saltar de branch observe as mudanças não commitadas;

## cria e saltar para outra branch(simultaneamente)
- git checkout -b nome_da_branch

## excluir branch [auxiliares]
- git branch -d nome_da_branch

## Unificar alterações da brach
- git merge nome_da_branch
  * agora as branchs estão no mesmo ponto
  
  * tecnicamente a 'mergeada' pode ser excluida
  
    

## Clonando meu repositorio (via SSH)
1. utilizando o GitBash;
2. foi copiada o endereço no gitHub;
   1. git@github.com:AlexDeveloperOne/beacademy-devstart-gitgithub.git

- git clone git@github.com:AlexDeveloperOne/beacademy-devstart-gitgithub.git

## Trabalhando com git stashes

- git stash (salva alteraçoes sem commit [que será feito depois])
- git stash --include-untracked [para incluir arquivos não rastreados].
- git stash pop (restaura alteraçoes salvas)
- git stash list (mostrar lista stashes)
- git stash pop stash@{1} (aplica stash especifico)

git stash reserva as alterações limpando seu STAGE. Assim você pode fazer outras coisas no sistema e depois voltar no stash e continuar seu trabalho.
'stash' só funciona em arquivos que estão sob rastreamento,  não funciona com arquivos untracked, mas para isso utilize o comando com o parametro (--include-untracked)

- git stash --include-untracked [para incluir arquivos não rastreados].

Se os arquivos existem simplesmente: 'git stash'

'git stash' - é importante que você dessa forma não é impedido de mudar de branch...
mas mudar constantemente de uma branch pode causar problemas [tu se perde]

## recuperar um stash específica

- git stash pop stash@{1}

## Gerando um conflito
- [@AlexDeveloperOne](https://github.com/AlexDeveloperOne) [dois devs modificaram essa linha].

- git checkout -b bug3
- git add .
- git commit -m 'resolvi o bug na sexta feira as 17:59'
- git push
- git push --set-upstream origin bug3
- git checkout main

pull request da branch bug3 <-> main [OK] sem conflito
deletei a branch bug3
[não existe outro dev] agora o outro dev vem com a branch bug4 e tenta mergear e dá conflito.

## REVISAO DOS PASSOS DO OUTRO DEV
- Criou a branch no PC dele;
- Trabalhou na branch;
- Fez o commit;
- Subiu a branch;
- por fim..
- git pull

<> finalizado a parte do pull request <>

## git Revert e Reset

Usado em casos muitos espicíficos, pois ficar mudando o passado no git é uma tarefa um pouco complexa. (alguma coisa sai do eixo).

## para reverter o ultimo commit

- git revert HEAD [PARA O ULTIMO COMMIT]

## para rverter um commit especifico

- git revert 73b7 [4 PRIMEIROS NUMEROS DA HASH]

## se der algum erro

- git revert --abort
