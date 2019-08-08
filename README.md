# Aula de Git

## Comandos básicos de terminal e git
```
git status                        //Mostra a situação do git neste repositório - executar sempre
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
git here
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

## Como clonar um repositório

```
git clone endereco_do_repositorio
cd nome_da_pasta_criada
add .
commit -m "nome do commit"
pull
push
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

### Em caso de emergência em uma tela azul
Ctrl+C:quit
