# ubuntu常用命令

1. 打开文件管理器
> nautilus

2. 以管理员身份打开文件管理器
> sudo nautilus

3. 在文件管理器中打开文件、文件夹
> nautilus file/folder

4. 文件夹改名
> mv filename filename

5. 删除一个空文件夹
> rmdir folder

6. 创建一个空文件
> touch file

7. 删除一个非空目录下的一切
> rm -rf

8. 删除一个文件或者多个文件
> rm file1 file2

9. 返回当前工作目录的绝对路径
> pwd

10. 复制文件
> cp dest1 dest2 將dest1的文件复制到dest2
> cp folder/* dest 將folder下的所以文件（不含子文件夹中的文件）复制到dest中
> cp -r folder dest 將folder下所有文件（包含子文件夹中欧给你的所有文件）复制到dest中

11. 输出文件到终端
> cat file

12. 输出文件到终端并显示行号
> cat -n file

13. 

## ln
`ln`主要用于在两个文件中创建链接，链接又分为 Hard Links (硬链接)和 Symbolic Links (符号链接或软链接)，其中默认为创建硬链接，使用 -s 参数指定创建软链接。
* 硬链接主要是增加一个文件的链接数，只要该文件的链接数不为 0 ，该文件就不会被物理删除，所以删除一个具有多个硬链接数的文件，必须删除所有它的硬链接才可删除。
* 软链接简单来说是为文件创建了一个类似快捷方式的东西，通过该链接可以访问文件，修改文件，但不会增加该文件的链接数，删除一个软链接并不会删除源文件，即使源文件被删除，软链接也存在，当重新创建一个同名的源文件，该软链接则指向新创建的文件。
* 硬链接只可链接两个文件，不可链接目录，而软链接可链接目录，所以软链接是非常灵活的。

> ln source dest       ### 为 source 创建一个名为 dest 的硬链接 <br/>
> ln -s source dest    ### 为 source 创建一个名为 dest 的软链接


