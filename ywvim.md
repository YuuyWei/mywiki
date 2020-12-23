# 支持鹤形的Vim中文输入法

这几天被Vim的中文输入法折磨的够呛。起初用的是插件[im-select](https://github.com/brglng/vim-im-select)，使用异步函数调用系统输入法切换接口，但是和插件Vimwiki有点冲突。唯一的解决方法就是使用同步调用，这对我这种强迫症患者来说绝对无法接受。

所以只能寻求Vim自带输入法的关爱。使用了大名鼎鼎的[Vimim](https://github.com/vimim/vimim)发现跑不起来，这就很尴尬了。接着又找到了[ywvim](https://www.vim.org/scripts/script.php?script_id=2662)，这个输入法本身没有小鹤输入法的词库，但是github上有支持小鹤音形的[分支](https://github.com/lotabout/ywvim)。

这个输入法的优点就是对音形码的支持比较完美，和官方的小鹤输入法体验相差无几。

缺点就是还不支持neovim的浮动窗口，只支持Vim8的弹出窗口，不过对我来说区别不大。因为本来小鹤输入法就很好的支持了盲打，那么我的输入法的折腾也到此为止了。
