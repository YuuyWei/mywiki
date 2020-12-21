# Learn Vim The Hard Way

Learn X the hard way is a series of books that teach people to learn 
the program languages they want.Here is the [book](https://learnvimscriptthehardway.stevelosh.com/)

- `echom` and `echo`
- options
    - `set number!` to toggle a boolean options
    - `set number?` to ask vim which value a option is.
    - `set numberwidth=4`
- map 
    - recursive map like `nmap dd O<esc>jddk`, this will never end
    - always use `noremap`
    - use `unmap` if you want
    - `<nop>` is to disable the key mapping to it 
    - abbreviations
        - `iabbrev adn and` change and to and in insert mode
- buffer mappings and options
    - `nnoremap <buffer> <leader> x dd` maps x to dd in a buffer
    - `setlocal nu` will only influence the current buffer
- auto commands
    -  `autocmd BufNewFile * :write`
        - `:autocmd BufNewFile * :write
             ^          ^ ^
             |          | |
             |          | The command to run.
             |          |
             |          A "pattern" to filter the event.
             |
             The "event" to watch for.`
    - `:autocmd BufWritePre *.html :normal gg=G`
    - `FileType` event
        - `:autocmd FileType javascript nnoremap <buffer> <localleader>c I//<esc>`
        - `:autocmd FileType python nnoremap <buffer> <localleader>c I#<esc>`
        - 
