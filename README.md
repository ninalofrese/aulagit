# Aula de Git

http://rogerdudler.github.io/git-guide/index.pt_BR.html

**Git** - é um software de versionamento que permite a sincronização do código com repositórios web\
**Git bash** - é um terminal onde você coloca os comandos\
**Github** - é um repositório web que compartilha o código com controle de versão usando o Git. É um portfólio para recrutadores verem a complexidade e as linguagens que trabalha, além de ser uma "rede social" de desenvolvedores. Similares: gitlab e bit bucket.

```
SUA MÁQUINA <-> NUVEM <-> OUTRA MÁQUINA
```

![Como funciona o git](git.png)

## Glossário

- **repositório** = projeto
- **branch** = é uma timeline (linha do tempo)
- **commit** = são pontos de alteração nos branchs
- **git flow** = é o fluxo de trabalho por branchs
- **merge** = união de dois branchs
- **clone** = cópia de uma branch de repositório online em repositório local
- **fork** = o fork é como um clone, mas dentro do github. Ele não baixa no computador, mas cria uma cópia na sua conta.
- **pull** = incorpora as mudanças de um repositório remoto para o branch local.
- **fetch** = atualiza as referências locais com relação às remotas, mas não faz merge com o branch local. Para incorporar, precisa executar um merge `git merge FETCH_HEAD` com o local.
- **pull request** = é um pedido que se faz ao dono do repositório para que este atualize o código dele com o seu código. Ou seja, você pede ao dono do projeto para adicionar as modificações ao repositório oficial.

## Comandos básicos de terminal e git

```
git status                        //Mostra a situação do git neste repositório - EXECUTAR SEMPRE
git remote                        //Mostra a etiqueta do arquivo de origem
git remote -v                     //Mostra a url do repositório de origem

pwd                               //Mostra caminho da pasta atual
cd ..                             //Vai para pasta acima
cd nome_da_pasta                  //entra na pasta citada
ls                                //lista os arquivos da pasta
ls -la                            //lista com detalhes de data, criação de arquivo...
mkdir nome_da_pasta               //cria uma pasta
touch nome_do_arquivo             //cria arquivo
rm nome_arquivo.txt               //remove arquivo definitivamente(sem perguntar)
rm -rf nome_da_pasta              //remove arquivo definitivamente(sem perguntar)
mv nome_do_arquivo novo_caminho   //move o arquivo para o novo_caminho
clear                             //esconde o histórico do console

```

## Como iniciar um repositório do computador
1. Criar uma pasta para o repositório e clicar com o botão direito e Git Bash Here
2. Inicializar o git nesta pasta (só é realizado em pastas que não têm o git inicializado)
```
git init
```
3. Criar um repositório no Github
4. Indicar o repositório web no git local
```
git remote add origin endereco_do_repositorio
```
O local pode ser a url do navegador, ou do botão Clone/ Download (selecionar SSH se estiver em um PC configurado com as suas chaves)
5. Adicionar os arquivos locais no repositório local
```
git add .
```
6. Etiquetar os arquivos com um comentário sobre os arquivos
```
git commit -m "Digite a mensagem"
```
7. Atualizar arquivos do repositório web para o local (Download)
```
git pull
```
Isso evita conflitos de versionamento, principalmente em casos de mais de uma pessoa comitando o mesmo repositório
8. Atualizar arquivos do repositório local para o web (Upload)

```
git push -u origin master
//não só faz o push como também seta que o seu branch padrão é o master, permitindo usar git push no futuro.
```

## Como clonar um repositório

```
git clone endereco_do_repositorio
cd nome_da_pasta_criada
add .
commit -m "nome do commit"
git pull
git push
```

## Problemas vivenciados com o git

### Mudar a url do remote (geralmente entre https e ssl)

Conferir qual a url do repositório
```
git remote -v
```

Modificar a url
```
git remote set-url nova_url
```

### Quanto tem erro "refusing to merge unrelated histories"

```
git pull --allow-unrelated-histories
```

### Erro "The current branch master has no upstream branch"

Isso acontece quando não há branch setado para ser usado sem argumentos, cru no git pull ou git push. Por isso, é importante ter o -u setado quando fizer o primeiro pull/ push. 

```
//git push nome_da_origem nome_do_branch
git push -u origin master
```

### Em caso de emergência em uma tela azul
Ctrl+C :quit

## O .gitignore
É um arquivo que você cria que lista todos os arquivos e pastas que devem ser ignorados no push.
Os commits após a criação deste arquivo serão ignorados.
Ainda não sei exatamente como, mas ele é bastante utilizado para ignorar arquivos com dados sensíveis, como senhas.

## Criar chave SSH em Linux

https://medium.com/@rgdev/como-adicionar-uma-chave-ssh-na-sua-conta-do-github-linux-e0f19bbc4265

```
ssh -T git@github.com
# Attempts to ssh to GitHub
```
