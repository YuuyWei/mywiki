# Vimwiki
:vim:

[Vimwiki](https://github.com/vimwiki/vimwiki) is a vim plug-in for personal wiki
users.  The plug-in uses wiki files by default but I want markdown Instead.
Fortunately it supports markdown files as well and need some additional work to
get it usable. 

I am always finding a note tool to recode my thoughts and tips I find.  I used
some note softwares before such as Evernote, Google Keep and Org-mode in Emacs.
None of them can I get used to thus I give up the idea temporarily.  Today I
finally get [Vimwiki](https://github.com/vimwiki/vimwiki) which is useful and
helpful to me.  By default Vimwiki uses a unfamiliar file type named vimwiki
ending with .wiki.  But I prefer to markdown, So It takes me some time to get
the plug-in work well.  ### How to switch wiki to markdown

On its official site, the author tells us a simple configuration.

```vim
let g:vimwiki_list = [{'path': '~/vimwiki/',
                      \ 'syntax': 'markdown', 'ext': '.md'}]
```
That's fine if you don't want to preview markdown in a browser.  If you do, a
problem come.  Vimwiki doesn't supports to generate html from files like
markdown except vimwiki.

So the plug-in [Markdown Preview for
Neovim](https://github.com/iamcco/markdown-preview.nvim) is needed.  Just
install it following the leading on the official site.

That's not enough to get the plug-in works well.  When you click the link that
Vimwiki generate on the browser, it can't lead to a correct file and return 404
instead.  To avoid this, add this to the vimrc and install
[markserv](https://github.com/markserv/markserv) by `npm install` on node.js.

```vim
let g:vimwiki_markdown_link_ext = 1

```
And an additional benefit is when you push your code to github, the link works
as you wish too.

There are the things that I am not satisfied with that when I open a vimwiki
file, the file type changes to vimwiki not markdown, some of my keyboard
mappings become disable and the [im
select](https://github.com/brglng/vim-im-select) plug-in works unexpectedly.  So
I set these options below to register markdown as vimwiki.

```vim
let g:vimwiki_ext2syntax = {
        \'.rmd': 'markdown',
        \'.Rmd': 'markdown',
        \'.markdown': 'markdown',
        \'.md': 'markdown',
        \'.mdown': 'markdown'}

let g:vimwiki_filetypes = ['markdown', 'pandoc']

```
And I disable some of the key mappings this way,

```vim
let g:vimwiki_key_mappings =
\ {
\   'all_maps': 1,
\   'global': 1,
\   'headers': 1,
\   'text_objs': 1,
\   'table_format': 1,
\   'table_mappings': 0,
\   'lists': 1,
\   'lists_return': 0,
\   'links': 1,
\   'html': 1,
\   'mouse': 0,
\ }

```
The `lists_return` disable the <CR> and <S-CR> in lists mapping, The official
version doesn't provide the `lists_return`, so I add this variable to
`g:vimwiki_key_mappings`. 

