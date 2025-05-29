# config_ambiente
Configuração de Ambiente de Trabalho
## 📌 Atualizar o Ubuntu Server
```sh
sudo apt update && sudo apt upgrade
```

## 📌 Instalar Node.js e npm
```sh
curl -fsSL https://deb.nodesource.com/setup_current.x | sudo -E bash -
sudo apt-get install nodejs -y
sudo apt install npm
```

## 📌 Instalar pacotes essenciais para Python/Django
```sh
sudo apt install -y python3-venv python3-dev default-libmysqlclient-dev build-essential
```
- python3-venv → Para criar ambientes virtuais
- python3-dev → Para compilar pacotes Python nativos
- default-libmysqlclient-dev → Para usar MySQL como banco de dados
- build-essential → Para compilar extensões nativas

## 📌 Instalar o MySQL Server
```sh
sudo apt install mysql-server
sudo systemctl enable mysql
sudo systemctl start mysql
```

## 📌 Reforçar a segurança do MySQl
```sh
sudo mysql_secure_installation
```
##### Opções recomendadas
- VALIDATE PASSWORD component (Y)
- levels of password validation policy (2)
- Remove anonymous users (Y)
- Disallow root login remotely (Y)
- Remove test database and access to it (N)
- Reload privilege tables now (Y)

## 📌 Criar usuario para acesso ao db MySQL 
```sh
sudo mysql -e "CREATE USER 'usuario'@'localhost' IDENTIFIED BY 'sua_senha';"
sudo mysql -e "GRANT ALL PRIVILEGES ON *.* TO 'usuario'@'localhost';"
sudo mysql -e "FLUSH PRIVILEGES;"

sudo mysql -e "CREATE USER 'usuario'@'%.%.%.%' IDENTIFIED BY 'sua_senha';"
sudo mysql -e "GRANT ALL PRIVILEGES ON *.* TO 'usuario'@'%.%.%.%';"
sudo mysql -e "FLUSH PRIVILEGES;"

```

## 📌 Instalar Tmux (Multiplex de terminal)
```sh
sudo apt install tmux
```

## 📌 Atualizar o editor vim
```sh
sudo add-apt-repository ppa:jonathonf/vim
sudo apt update
sudo apt install vim
```

## 📌 Instalar o ZSH
```sh
sudo apt install zsh
```

## 📌 Instalar o OhMyZSH
[link ohmyzsh github](https://github.com/ohmyzsh/ohmyzsh)
```sh
sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```
## 📌 Configuração extra para Zsh
##### No Oh My Zsh, adicionar plugins úteis no .zshrc, como autossugestões e realce de sintaxe

```sh
git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting
```
## 📌 Editar dotfile .zshrc
```sh
vim .zshrc
```
> Alterar linha ZSH_THEME="..." para ZSH_THEME="fino"
> Alterar linha plugins=(git) para plugins=(git zsh-autosuggestions zsh-syntax-highlighting)
> Adicionar no final essas duas linhas
> source ~/.oh-my-zsh/custom/plugins/zsh-autosuggestions/zsh-autosuggestions.zsh
> source ~/.oh-my-zsh/custom/plugins/zsh-syntax-highlighting/zsh-syntax-highlighting.zsh

## 📌 Configurar ZSH como shell padrão
```sh
chsh -s $(which zsh)
```

## 📌 Instala o pipx
```sh
sudo apt install pipx
pipx ensurepath
```

## 📌 Instala o poetry
```sh
pipx install poetry
pipx inject poetry poetry-plugin-shell
```



## 📌 Personalizar o VIM
Copiar pacotes no diretório ~/.vim/pack/git-plugins/start

##### vim-startify
Cria uma tela inicial personalizada no Vim, exibindo os arquivos recentemente abertos, diretórios, entre outras opções. [link github](https://github.com/mhinz/vim-startify)

##### ctrlp.vim
CtrlP é um plugin para navegação de arquivos de maneira rápida. [link github](https://github.com/ctrlpvim/ctrlp.vim.git)

##### vim-bookmarks
Permite marcar linhas de código no Vim, facilitando a navegação entre elas. [link github](https://github.com/MattesGroeger/vim-bookmarks)

##### NERDTree
Explorar e navegar pelo sistema de arquivos dentro do editor. [link github](https://github.com/preservim/nerdtree)

##### NERDCommenter
Facilita a adição, remoção e alternância de comentários no código, suportando múltiplas linguagens de programação. [link github](https://github.com/preservim/nerdcommenter)

##### indentLine
Exibir linhas verticais para indicar a indentação no código, o que ajuda a visualizar melhor a estrutura do código. [link github](https://github.com/Yggdroot/indentLine)

##### vim-polyglot
Suporte para múltiplas linguagens de programação de forma eficiente, incluindo destaque de sintaxe e outras funcionalidades específicas para cada linguagem. [link github](https://github.com/sheerun/vim-polyglot.git)

##### python-syntax
Melhorar a sintaxe de Python no Vim, oferecendo destaque de sintaxe aprimorado para código Python. [limk github](https://github.com/vim-python/python-syntax) 

##### vim-python-docstring
Gerar docstrings de Python automaticamente no formato correto (como Google, NumPy, ou outros formatos populares) quando você digita as docstrings para funções ou classes. [link github](https://github.com/pixelneo/vim-python-docstring)

##### emmet-vim
Ferramenta para expandir abreviações de HTML e CSS. [link github](https://github.com/mattn/emmet-vim.git)

##### vim-fugitive
Integrar o Git diretamente no Vim, permitindo operações como commit, push, pull e muito mais, diretamente do editor. [link github](https://github.com/tpope/vim-fugitive)

##### Awesome vim color schemes
Coleção de esquemas de cores para o VIM. [limk github](https://github.com/rafi/awesome-vim-colorschemes) 

##### vim-airline
Adicionar uma barra de status elegante e funcional ao Vim, com muitos recursos como exibição de informações sobre o arquivo, branch Git, entre outros. [limk github](https://github.com/vim-airline/vim-airline) 

##### vim-airline-themes
Coleção de temas para o vim-airline. [link github](https://github.com/vim-airline/vim-airline-themes)

##### vim-code-dark
Tema para o Vim inspirado no visual do Visual Studio Code, com um esquema de cores escuro que oferece boa legibilidade. [link github](https://github.com/tomasiser/vim-code-dark)

##### vim-devicons
Adiciona ícones para diferentes tipos de arquivos no Vim, melhorando a visibilidade e organização ao trabalhar com múltiplos arquivos no seu editor. [link github](https://github.com/ryanoasis/vim-devicons.git)

##### ale (Asynchronous Lint Engine)
Faz análise de código em tempo real e correção automática de arquivos. Ele funciona como um linter e um formatter, verificando erros no código e aplicando ajustes conforme necessário. [link github](https://github.com/dense-analysis/ale)

##### coc-nvim
O CoC.nvim (Conqueror of Completion) é um LSP (Language Server Protocol) client para Vim e Neovim. Ele transforma o Vim em uma IDE poderosa, fornecendo:

✅ Autocompletar inteligente (como no VS Code)
✅ Linting (destaque de erros e sugestões)
✅ Formatação de código (com Prettier, Black, etc.)
✅ Suporte a múltiplas linguagens via servidores LSP
✅ Snippets e sugestões contextuais
✅ Integração com ferramentas como ESLint, Pyright, Pylance
[link github](https://github.com/neoclide/coc.nvim.git)

1. :CocInstall coc-html → Suporte a HTML
2. :CocInstall coc-git → Integração com Git dentro do Vim
3. :CocInstall coc-tsserver → Suporte a TypeScript e JavaScript
4. :CocInstall coc-sh → Suporte a Shell Script
5. :CocInstall coc-json → Suporte a JSON
6. :CocInstall coc-htmldjango → Suporte a templates Django
7. :CocInstall coc-css → Suporte a CSS
8. :CocInstall coc-pyright → Suporte a Python

```sh
git clone https://github.com/mhinz/vim-startify.git ~/.vim/pack/git-plugins/start/vim-startify
git clone https://github.com/ctrlpvim/ctrlp.vim.git ~/.vim/pack/git-plugins/start/ctrlp.vim
git clone https://github.com/MattesGroeger/vim-bookmarks.git ~/.vim/pack/git-plugins/start/vim-bookmarks
git clone https://github.com/preservim/nerdtree.git ~/.vim/pack/git-plugins/start/nerdtree
git clone https://github.com/preservim/nerdcommenter.git ~/.vim/pack/git-plugins/start/nerdcommenter
git clone https://github.com/Yggdroot/indentLine.git ~/.vim/pack/git-plugins/start/indentLine
git clone https://github.com/sheerun/vim-polyglot.git ~/.vim/pack/git-plugins/start/vim-polyglot
git clone https://github.com/vim-python/python-syntax.git ~/.vim/pack/git-plugins/start/python-syntax
git clone https://github.com/pixelneo/vim-python-docstring.git ~/.vim/pack/git-plugins/start/vim-python-docstring
git clone https://github.com/mattn/emmet-vim.git ~/.vim/pack/git-plugins/start/emmet-vim
git clone https://github.com/tpope/vim-fugitive.git ~/.vim/pack/git-plugins/start/vim-fugitive
git clone https://github.com/rafi/awesome-vim-colorschemes.git ~/.vim/pack/git-plugins/start/awesome-vim-colorschemes
git clone https://github.com/vim-airline/vim-airline.git ~/.vim/pack/git-plugins/start/vim-airline
git clone https://github.com/vim-airline/vim-airline-themes.git ~/.vim/pack/git-plugins/start/vim-airline-themes
git clone https://github.com/tomasiser/vim-code-dark.git ~/.vim/pack/git-plugins/start/vim-code-dark
git clone https://github.com/ryanoasis/vim-devicons.git ~/.vim/pack/git-plugins/start/vim-devicons
git clone https://github.com/dense-analysis/ale.git ~/.vim/pack/git-plugins/start/ale
git clone --branch release https://github.com/neoclide/coc.nvim.git ~/.vim/pack/git-plugins/start/coc.nvim
```

1. Instalar os linters e formatadores para Python (Pylint, Flake8, Black)
```sh
pip install black pylint flake8 
```
- black → Formatador de código
- pylint → Linter completo para Python
- flake8 → Verificador de estilo

adicionar no dotfile .vimrc
```vim
let g:ale_fix_on_save = 1
let g:ale_fixers = {
  \ 'python': ['black'],
  \}
```

2. Instalar os linters e formatadores para JavaScript, TypeScript, JSON, HTML, CSS (Prettier)
```sh
sudo npm install -g eslint prettier
```
- eslint → Ferramenta para análise e padronização de código JavaScript e TypeScript
- prettier → Formatador de código para JS, TS, JSON, HTML, CSS

adicionar no dotfile .vimrc
```vim
let g:ale_linters = {'javascript': ['eslint']}
let g:ale_fixers = {
  \ 'javascript': ['prettier'],
  \ 'typescript': ['prettier'],
  \ 'json': ['prettier'],
  \ 'html': ['prettier'],
  \ 'css': ['prettier'],
  \}
```

