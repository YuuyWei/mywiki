# Auto format texts in fixed width in Vim
:vim:

## 怎样让Vim保持78一换行
以前老式的机器上屏幕一行只能显示80个字符，如果超过了这个值之后的字符就显示不出
了，因此人们就规定一行的长度不能超过78个字符。

而Vim里可以设置超过一定的字符长度自动换行，并且额外提供了支持Unicode的选项。
`textwidth`的值代表每行的最大长度，`formatoption+=m`则是使Vim支持中文等文字的
自动折行操作。

```vim
set textwidth=78
set formatoptions+=m
```

关于Vim里面的关于format-options的其他选项，可以查看帮助

```vim
:h mbyte-options
:h fo-table
```
