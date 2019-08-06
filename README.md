# Aula de Git

## Comandos básicos de terminal e git
```
**git remote** - Mostra a etiqueta do arquivo de origem

```

## Como iniciar um repositório do computador
1. Criar uma pasta para o repositório e clicar com o botão direito e Git Bash Here
2. Inicializar o git nesta pasta (só é realizado em pastas que não têm o git inicializado)
``` git here ```
3. Criar um repositório no Github
4. Indicar o repositório web no git local
``` git remote add origin endereco_do_repositorio ```
O local pode ser a url do navegador, ou do botão Clone/ Download (selecionar SSH se estiver em um PC configurado com as suas chaves)
5. Adicionar os arquivos locais no repositório local
``` git add . ```
6. Etiquetar os arquivos com um comentário sobre os arquivos
``` git commit -m "Digite a mensagem" ```
7. Atualizar arquivos do repositório web para o local (Download)
``` git pull ```
Isso evita conflitos de versionamento, principalmente em casos de mais de uma pessoa comitando o mesmo repositório
8. Atualizar arquivos do repositório local para o web (Upload)

## Problemas vivenciados com o git
