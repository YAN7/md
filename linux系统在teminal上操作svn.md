# 在teminal上操作svn

## 前言安装的过程



## 安装svn

> sudo apt-get install subversion-tools
> 输入 svn --version验证是否安装成功

## svn常用命令

##### svn checkout url(服务器上的目录) 简写 svn co url
> 从服务器上新建一个工作目录到本地

##### svn update filename 简写 svn up filename

> 更新代码 如果后面不跟文件名，则默认更新该目录下的所有文件及子文件

##### svn commit -m "msg" filenname 简写 svn ci -m "" filename
> 提交代码 如果后面不跟文件名，则默认提交该目录下的所有文件及子文件

##### svn add * --force
> 添加没有加入svn版本控制的文件 svn是自动判断哪些文件是没有添加的却没有设置被忽略的文件

##### svn delete -m "msg" filename 简写 svn del/remove/rm
> 删除文件

##### svn resolved filename 
> 解决冲突

##### svn log filename
> 查看日记

##### svn diff filename 简写： svn di
> 比较差异

##### svn mkdir filename/url
> 创建纳入版本控制的新目录
