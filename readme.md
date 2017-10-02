[Vim 8][1]/[NeoVim][2] [configuration][5]
====================

See: http://liuchengxu.org/posts/use-vim-as-a-python-ide/

    git clone git://github.com/vestrobaa/dotvim8.git ~/.vim 
    ln -s ~/.vim/vimrc ~/.vimrc
    ln -s ~/.vim/gvimrc ~/.gvimrc

On Windows

    Configure environment variable home=%userprofile%

    git clone git://github.com/vestrobaa/dotvim8.git %userprofile%\vimfiles
    mklink /h _vimrc %userprofile%\vimfiles\vimrc
    mklink /h _gvimrc %userprofile%\vimfiles\gvimrc


Plugins
-------

Tools
-----

[tpope/vim-fugitive][10]
[tpope/vim-unimpaired][11] navigation
[tpope/vim-surround][12] text markup
[tpope/vim-capslock][13] soft caps lock
[ctrlpvim/ctrlp.vim][14] fuzzy file finder

Format
------

[google/yapf][20] Python formatter

Pretty
------

Plug 'bling/vim-airline'
Plug 'NLKNguyen/papercolor-theme'
Plug 'sjl/badwolf'
Plug 'lifepillar/vim-wwdc17-theme'
Plug 'lifepillar/vim-wwdc16-theme'
Plug 'liuchengxu/space-vim-dark'

- [Metarw][120], [git][122] and [gdrive][121] virtual paths
- [Paper][100], [bad wolf][102] and [base16][101] colors
- [Syntastic][50] syntax checker
- ...


Tools
-----

- [Pandoc][91] universal document converter
- [Exuberant Ctags][90] variable tagger
- [google/yapf][200] python formatter


Usage
=====

Keyboard

    let mapleader = ","
    let g:mapleader = ","
    inoremap fq <esc>
    inoremap FQ <esc>
    inoremap <esc> <nop>
    map <Left> :echo repeat('←', winwidth(0)/4)<cr>
    map <Right> :echo repeat('→', winwidth(0)/4)<cr>
    map <Up> :echo repeat('↑', winwidth(0)/4)<cr>
    map <Down> :echo repeat('↓', winwidth(0)/4)<cr>

Files

-   Open file `<leader>fr`
-   Open buffer `<leader>fb`
-   History `<leader>g`

Format

-   Custom CSV `<leader>cs`
-   XML `<leader>fx`
-   Indent `G=`

Diff

-   Put `dp`
-   Get `do`
-   Next chunk `]c`
-   Previous chunk `[c`

Surround text  

-   cs<from><to>, cs"', cst<to> - Change surrounding character, string or <tag> combination  
-   ds" - Delete surrounding "  
-   ysiw] - Yank and surround the inner word with ]. Use [{( or ]}) to include a space
-   yss" - Yank and surround the line with "  
-   ys$" - Yank and surround the rest of the line with "  
-   <visual>S" - Surround makred text with "

Database

-   :DBPromptForBufferParameters - Connect to the database
-   <leader>se[ |l] - SQL execute ( )visual selection, (l)ine, 
-   <leader>s[t|T|w|a] - SQL select from (t)able, (T)op from table, from table (w)here, from <(a)sk table name>
-   <leader>sd[t|v|p] - SQL describe (t)able, (v)iew, (p)rocedure
-   <leader>sl[t|v|p|c] - SQL list (t)able, (v)iew, (p)rocedure, (c)olumn
-   <leader>sh - SQL history

Tags

-   Generate tags in root folder `<leader>tf`
-   Generate tags in git folder `<leader>tg`
-   Generate tags manually `ctags -R .`
-   Jump to a tag   `<c-]>` or back `<c-t>`
-   Code options    `<c-x><c-o>`
-   Code completion `<c-x><c-]>`


Python-mode

-   Lint toggle `PymodeLintToggle`
-   Rope toggle         `RopeToggle`
-   Run code            `<leader>r`
-   Breakpoint          `<leader>b`
-   Text object Method  `M`, and `[[, [M, ]M, ]]`
-   Text object Class   `C`, and `[[, [C, ]C, ]]`

Completion

-   Previous match `<c-p>`
-   Next match `<c-n>`
-   Complete with tag           `<c-x><c-]>`
-   Complete with file          `<c-x><c-f>`
-   Complete with Omnicomplete  `<c-x><c-o>`
-   Complete with line          `<c-x><c-l>`


Submodules
----------

Upgrade

    git submodule foreach git pull origin master
    git submodule foreach git submodule init
    git submodule foreach git submodule update

Add

    cd ~/.vim
    git submodule init
    git submodule add git://github.com:/author/whatever.git bundle/whatever
    git commit -m 'Added submodule whatever'
    git push

Remove

    vim .git/config # remove the submodule x's lines
    vim .gitmodules # remove the submudule x's lines
    rm -rf .git/modules/bundle/x
    git rm --cached bundle/x
    rm -rf bundle/x
    git commit

[1]: http://www.vim.org/
[2]: http://neovim.io
[5]: https://github.com/vestrobaa/dotvim8


[31]: https://github.com/tpope/vim-fugitive
[20]: http://kien.github.io/ctrlp.vim/

[100]: https://github.com/NLKNguyen/papercolor-theme.git
[102]: https://github.com/sjl/badwolf.git


[2]: https://chrome.google.com/webstore/detail/jmchmkecamhbiokiopfpnfgbidieafmd 
[3]: http://daringfireball.net/projects/markdown/ 
[4]: https://github.com/tpope
[6]: http://github.com
[21]: https://github.com/Lokaltog/vim-easymotion
[22]: https://github.com/tpope/vim-unimpaired
[30]: http://http://git-scm.com/
[32]: https://github.com/tpope/vim-git
[32]: https://github.com/sjl/gundo.vim
[40]: http://daringfireball.net/projects/markdown/ 
[41]: https://github.com/tpope/vim-markdown
[42]: https://github.com/plasticboy/vim-markdown
[50]: https://github.com/scrooloose/syntastic
[51]: https://github.com/vim-scripts/pep8
[52]: http://www.python.org/
[63]: http://github.com/tpope/vim-endwise
[64]: http://github.com/tpope/vim-cucumber
[70]: https://github.com/vim-scripts/dbext.vim
[80]: https://github.com/croaker/mustang-vim
[81]: https://github.com/Lokaltog/vim-distinguished
[82]: https://github.com/tpope/vim-surround.git
[83]: https://github.com/tpope/vim-capslock.git
[90]: http://ctags.sourceforge.net
[91]: http://pandoc.org/
[92]: http://cscope.sourceforge.net/cscope_vim_tutorial.html
[93]: http://opengrok.github.io/OpenGrok/
[110]: https://github.com/junegunn/goyo.vim.git
[120]: https://github.com/kana/vim-metarw.git
[121]: https://github.com/mattn/vim-metarw-gdrive.git
[122]: https://github.com/kana/vim-metarw-git.git
[123]: https://github.com/tpope/vim-vinegar.git
