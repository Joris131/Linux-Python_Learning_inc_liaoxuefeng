# 目录
## 01. 列表更新
## 02. 安装可用更新
## 03.在linux中终止某个进程
## 04. 终端退出Python
## 05. Linux的小数转化
## 06. 查看IP地址
## 08. 查询Linux命令
## 09. 如何删除ubuntu用户
## 10. Ubuntu中Libre的字体问题
## 11. 有关apt-get
## 12. 有关解压和压缩
## 13. 正则表达式
## 14. 关于rm
## 15. 关于ls
## 16. 添加环境变量的一般方法
## 17. 安装deb软件包
## 18. Ubuntu创建shortcut
## 19. 设置文件（夹）权限
## 20. cd命令返回上一级及下一级文件夹
## 21. 进入root
## 22. to see a tab deliminated file in terminal

z.进入root：sudo -i
## 01. 列表更新
    sudo apt-get update

## 02.安装可用更新
    sudo apt-get upgrade

## 03.在linux中终止某个进程
    kill 1234（进程ID）
    
## 04. 终端退出Python：Ctrl+D

## 05. Linux 中的小数属于浮点数，一般的输入会视为整数，所以想要有小数时，需用到 float 相关的转化，例如：

### [ ] 是list，是可变的；
### （  ） 是 tuple，其中的元素是不可变的；
### {key-value } 是dict，其中的key是不可变的,但dict是可变的。

## 06.查看IP地址：
    ifconfig -a

## 08. Linux的命令有很多，但不可能全部都记住，所以要学会查询相关命令，可有2个方法：

## 09. 如何删除ubuntu用户？
### ubuntu删除用户同样是在终端下操作的，需要注意的是，如果要删除的用户当前已登陆，是删除不掉的，必须注销掉当前用户切换为另一个用户下，才能删除。举个例子，刚才我新建立了一个用户为 yang 的用户，例如我现在用用户 yang 登陆了桌面，此时如果我想删除 yang 这个用户，是删除不掉的。正确的操作方法是，### 我注销掉 yang，然后使用 root 登陆到桌面，再删除 yang 即可。
    sudo userdel username

## 10. Ubuntu中Libre的字体问题
用Liberation Serif替代Times new Roman；Ubuntu 默认的简体中文字体有三种：AR PL UKai 是一种楷体，AR PL UMing 是一种宋体，Droid Sans Fallback 是一种黑体。最后一种负责在 Ubuntu 平台上显示中文。

## 11. 关于apt-get
apt-get autoclean:
    如果你的硬盘空间不大的话，可以定期运行这个程序，将已经删除了的软件包的.deb安装文件从硬盘中删除掉。如果你仍然需要硬盘空间的话，可以试试apt-get clean，这会把你已安装的软件包的安装包也删除掉，当然多数情况下这些包没什么用了，因此这是个为硬盘腾地方的好办法。
apt-get clean:
    类似上面的命令，但它删除包缓存中的所有包。这是个很好的做法，因为多数情况下这些包没有用了。但如果你是拨号上网的话，就得重新考虑了。
apt-get autoremove:
    删除为了满足其他软件包的依赖而安装的，但现在不再需要的软件包。
其它：
apt-get remove 软件包名称：
    删除已安装的软件包（保留配置文件）。
apt-get --purge remove 软件包名称：
     删除已安装包（不保留配置文件)。

## 12.
### 12.1 Linux unzip解压文件到某个目录下面：
unzip <your zip file> -d <your targeted directory>

## 13.正则表达式：
### 13.1 grep

^ 表示以什么为开头
$ 表示以什么为结尾
^$ 表示空行（注意文本中没有这两个符号，不然要转义）
[a-z] 表示a-z的任意字符
[^a-z] 表示以非a-z为开头的字符(会把空行也过滤）
. 表示任意字符（除了空行，真正的任意字符——万能匹配是 .* ）
* 表示0或者任意个字符
? 表示0个或者1个（要加 -E ，表示允许扩展表达式，或者把grep改为egrep)
+ 一次或多次（要加 -E ，表示允许扩展表达式，或者把grep改为egrep)
\{m,n\} 重复m到n次
| 或者（要加 -E ，表示允许扩展表达式，或者把grep改为egrep）

### 13.2 sed：
例如，要获取ip地址，命令为：
ifconfig | grep 'inet addr:192' | sed 's/^.*addr:\(.*\) Bc.*/\1/g' 

sed

### 13.3 awk:
例如，要获取ip地址，命令为：
ifconfig | awk -F'[ :]+' '/inet addr:192/{print $4}'

## 14.关于rm:

    rm -rf #可用删除文件夹

## 15.关于ls:

    ls -ah #可以显示.开头的文件
    ls -l #可以显示储存和权限等数据
    ls -lh #If we wish to use human-readable sizes
    
## 16.添加  环境变量的一般方法：

    export PATH=/you/path/.../bin:$PATH
    
## 17.安装deb软件包：
 
    sudo apt-get install --no-install-recommends gnome-panel

## 18.Ubuntu创建shortcut：

    sudo apt-get install --no-install-recommends gnome-panel
    gnome-desktop-item-edit ~/Desktop/ --create-new

## 19.加入-R 参数，就可以将读写权限传递给子文件夹例如：
    
    chmod -R 777 /home/mypackage
### 一般文件如下：
    chmod u=rwx,go=rx .bashrc 
    chmod u=rwx,g=rx,o=r filename
    chmod 754 filename
    chmod 777 filename
#### 注意喔！那个 u=rwx,go=rx 是连在一起的，中间并没有任何空格符！

## 20.cd命令返回上一级及下一级文件夹
 
    cd ../
    cd ..

## 21. 进入root

### sudo -i

## 22. to see a tab deliminated file in terminal
    column -t -s $'\t' 1805409757.clean.rmhost.20M_metaphlan_bugs_list.tsv | less -S
