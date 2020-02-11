# md-img-paste.vim
Yet simple tool to paste images into markdown files
use it as p/P command in normal mode

## Use Case
You are editing a markdown file and have an image on the clipboard and want to paste it into the document as the text `![](img/${time}.png)`. Instead of first copying it to that directory, you want to do it with a single `p/P` key press in Vim. So it hooks `p/P`, checks if you are editing a Markdown file, saves the image from the clipboard to the location  `img/${time}.png`, and inserts `![](img/${time}.png)` into the file.

## Installation

Using Vundle
```
Plugin 'zk4/md-img-paste.vim'
```

## Usage
Add to .vimrc
```
autocmd FileType markdown nmap <buffer><silent> p :call mdip#MarkdownClipboardImage()<CR>
autocmd FileType markdown nmap <buffer><silent> P <up>:call mdip#MarkdownClipboardImage()<CR>
autocmd FileType vimwiki nmap <buffer><silent> p :call mdip#MarkdownClipboardImage("wiki")<CR>
autocmd FileType vimwiki nmap <buffer><silent> P <up>:call mdip#MarkdownClipboardImage("wiki")<CR>

" there are some defaults for image directory and image name, you can change them
" let g:mdip_imgdir = 'img'
" let g:mdip_imgname = 'image'
```

## Acknowledgements
I'm not yet perfect at writing vim plugins but I managed to do it. Thanks to [Karl Yngve Lervåg](https://vi.stackexchange.com/users/21/karl-yngve-lerv%C3%A5g) and [Rich](https://vi.stackexchange.com/users/343/rich) for help on [vi.stackexchange.com](https://vi.stackexchange.com/questions/14114/paste-link-to-image-in-clipboard-when-editing-markdown) where they proposed a solution for my use case.

