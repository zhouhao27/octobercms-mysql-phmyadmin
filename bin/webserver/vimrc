set nocompatible              " be iMproved, required
filetype off                  " required

" set the runtime path to include Vundle and initialize
set rtp+=~/.vim/bundle/Vundle.vim
call vundle#begin()

" let Vundle manage Vundle, required
Plugin 'VundleVim/Vundle.vim'

Plugin 'tpope/vim-fugitive'
Plugin 'git://git.wincent.com/command-t.git'
Plugin 'https://github.com/bling/vim-airline'
Plugin 'https://github.com/scrooloose/nerdtree'
nnoremap <F3> :NERDTreeToggle<CR>
autocmd bufenter * if (winnr("$") == 1 && exists("b:NERDTree") && b:NERDTree.isTabTree()) | q | endif

call vundle#end()            " required
filetype plugin indent on    " required

"开启语法高亮
syntax on
set tabstop=2
set shiftwidth=2
"使用空格替换TAB
set expandtab 
set autoindent
set cursorline
set textwidth=80
set wrap
set hlsearch
set encoding=utf-8

"显示当前的行号列号：
set ruler
"在状态栏显示正在输入的命令
set showcmd

"Color for bracket 
colorscheme desert
hi MatchParen ctermbg=Yellow guibg=lightblue
"显示行号：
set number
"为方便复制，用<F2>开启/关闭行号显示:
nnoremap <F2> :set nonumber!<CR>:set foldcolumn=0<CR>

set modeline

" For Python
let python_highlight_all=1
au Filetype python set tabstop=2
au Filetype python set softtabstop=2
au Filetype python set shiftwidth=2
au Filetype python set textwidth=80
au Filetype python set expandtab
au Filetype python set autoindent
au Filetype python set fileformat=unix
autocmd Filetype python set foldmethod=indent
autocmd Filetype python set foldlevel=99
