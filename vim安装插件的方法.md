# vim 安装插件的方法

## 前言


> 最近迷上了用vim写madkdown，因为要安装了vim上相关的madkdown插件，顺便把自己安装插件的折腾过程记录下来

### step1 安装vim的插件管理器vundle

1. `git clone https://github.com/VundleVim/Vundle.vim.git ~/.vim/bundle/Vundle.vim`


### step2 修改vim的配置文件


1. 配置文件在`/etc/vim`里面(ubuntu) ,
> 使用mac的则放在`/usr/share/vim`中,但是这是系统级文件，一般没有权限修改（反正我是没有修改成功~）,解决办法是在`~`目录下新建一个.vimrc文件，这是用户级文件，可以随便修改.

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

#### 在mac上配置vim高亮

1. mac上用vim编辑是完全没有任何高亮的，打开任何文件都是白色字体，作为一个颜值控这怎么能忍？
2. 首先在新建一个文件夹,将vim配色主题包clone下来`it clone git://github.com/altercation/solarized.git`，这是包括所有的配色方案的，如果只想用vim配色，可以clone这个[Vim respostor]y(https://github.com/altercation/vim-colors-solarized)  (我用的是这个)
3. 将`solarized.vim`复制到`~/.vim/colors`目录下，一般情况下是没有colors这个目录的，你需要先新建一个才能复制，否则会失败
```
cd cd vim-colors-solarized/colors
cp ./solarized.vim ~/.vim/colors

```
4. 打开`~/.vimrc`， 将以下代码复制进去

```
syntax enable

if has('gui_running')
    set background=light
else
    set background=dark
endif

colorscheme solarized
```

5. 也可以只设置一种主题(推荐黑色主题)

```
syntax enable

set background=dark

colorscheme solarized
```

6. 默认的背景的灰黄灰黄的，个人不喜欢,但是可以把背景色设置为自己terminal的背景色，

```
let g:solarized_termtrans=1
```

> 注意，这句代码要加在`colorscheme solarized`之前才能起效.

7. 至此，大功告成！更多配色的设置可以去[solarized-github](https://github.com/altercation/solarized)寻找。



> [vim常用命令](http://blog.csdn.net/wklken/article/details/7533272)

