----------------- Curso de Git Udemy ----------------

----- Setores do Git
	- area de trabalho
	- stage (onde ficam arquivos adicionados(add) antes do commit)
	- head, branch, 

----- Palavras-Chave:
- prefixo: git <command>

- commands: init, status, add, commit, log, diff, reset,branch, checkout, remote, pull, fetch, merge, remote, stash, shortlog, show, revert  

- properties: HEAD, HEAD~1, HEAD~2, --soft, --hard, --help, --decorate, --author="Nome", --graph, -sn, --name-only
 		  

----- Comandos do Curso:

	git commit -am ('para arquivos que já existiram no stage)
	git clone git@github.com:And-P/github-course.git new_dir
	git log --decorate (--author="Nome", --graph)
	git shortlog (-sn)
	git show "HashCode"
	git diff (--name-only)
	git checkout -b novo-branch
	git branch
	git stash (apply, list, show, drop, clear, create, store)
	git config --global alias.s status 
	
--- Desfazendo Coisas no Git 

	git checkout "Nome_Arquivo" (retira modificação do arquivo ainda na área de trabalho(unstaged file))
	git reset HEAD (retira o arquivo do stage-area, para depois usar o comando git checkout e retirar as alterações indesejáveis) 
	git reset "HashCode"(--soft, --mixed, --hard) retira commits
	git revert "Hash-Code" (hash do commit a ser removido)
	
--Branch
	
	git branch (lista os branchs disponíveis)
	git checkout -b novo-branch (cria novo-branch)
	git checkout novo-branch (entra em novo-branch)
	git branch -D nome-branch (deleta nome-branch)

--Tag
	git tag (mostra tags geradas)
	git tag -a 1.0.1 -m "Mensagem link" (cria tag)
	git push origin master --tags

--- Repositorio Remoto - GitHub
	obs: antes, configurar a chave SSH 

	git remote add origin git@github.com:And-P/Projeto.git
	git remote -v ('lista os repositorios remotos disponíveis')

	git push -u origin master ('remoto' - 'branch'- o -u crackeia o endereço, depois é só digitar git push como atalho)	

	git clone git@github.com:And-P/github-course.git Pasta_Clone

--- GitHub - Fork
	Fazer um fork(no GitHub) de projetos de outros domínios, traz uma cópia do projeto para meu repositório remoto. 

--- .gitignore 
   
	- criar um arquivo .gitignore
	
	O .gitignore é um arquivo de texto, onde anotamos o que deve ser ignorado pelo git. 
	- *.json (*.extensao-do-arquivo): ignora todos os arquivos com tal extensão

	- nome_do_arquivo : ignora o arquivo especificado
	- um repositório, no https://github.com/github/gitignore, especifica padrões para desenvolvimento em varias plataformas(java, etc...) 

-----Apagando Tags e Branchs em Repositórios Remotos

	git tag -d cod-tag (ex. 1.0.1 - só apaga local)
	git push origin :1.0.0 (apaga tag remota)
	git push origin :master (apaga branch remoto)


----- Observações Gerais:

- falando de diff: "sempre use o git diff antes de fazer um commit".
- git reset: "usa-se a HashCode anterior ao commit que se quer retirar"
- revert: "ele retira as alterações, informa na log o revert e não apaga o commit de origem do problema da log - o revert serve pra resetar o arquivo sem perder as alterações que foram feitas"


