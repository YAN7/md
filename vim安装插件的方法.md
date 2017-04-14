# vim 安装插件的方法

## 前言

> 最近迷上了用vim写madkdown，因为要安装了vim上相关的madkdown插件，顺便把自己安装插件的折腾过程记录下来

### step1 安装vim的插件管理器vundle

1. `git clone https://github.com/VundleVim/Vundle.vim.git ~/.vim/bundle/Vundle.vim`

### step2 修改vim的配置文件

1. 配置文件在`/etc/vim`里面

2. 以管理员权限打开`sudo vi vimrc`,将一下代码复制进去

```
set nocompatible    " be iMproved, required
filetype off " required
" 启用vundle来管理vim插件
set rtp+=~/.vim/bundle/Vundle.vim
call vundle#begin()
" 安装插件写在这之后
" let Vundle manage Vundle, required
Plugin 'VundleVim/Vundle.vim'
" 安装插件写在这之前
call vundle#end() " required
filetype plugin on 
" required" 常用命令
" :PluginList - 查看已经安装的插件
" :PluginInstall - 安装插件
" :PluginUpdate - 更新插件
" :PluginSearch - 搜索插件，例如 :PluginSearch xml就能搜到xml相关的插件
" :PluginClean - 删除插件，把安装插件对应行删除，然后执行这个命令即可
" h: vundle - 获取帮助

```

3. 要安装的插件都要写进vimrc配置文件中，写入的位置在注释中都有说明的，不要放错了 

### 打开vim安装插件

1. 使用`sudo vim`打开vim
2. 输入`:PluginInstall`安装插件
3. 在输入区，即左下角出现`done`字样则表示安装成功
4. 输入`:wq`保存推出则大功告成！


