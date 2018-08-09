# git的作用
git是一个安装程序，可以利用git在本地直接管理github仓库的托管代码

# git的工作区域：分为三个部分
  1.工作区（Working Directory）：在这个区域进行操作，添加、编辑、修改
  2.暂存区：把工作区的文件暂时的提交到这个区域，此时使用git status查看，文件是标红的
  3.GitHub仓库：此时才是提交到github的代码仓库中。
  
# git初始化操作（本地操作）
    1.设置用户名
    新建一个文件夹，也就是仓库（respository）
        git config --global user.name "用户名"
        git config --global user.email "邮箱"
        这个语句设置了在GitHub中显示是谁提交的文件。   pwd命令显示当前文件夹的path
        两条设置语句都要使用，少了一条都不行
    2.建立一个仓库（respository）
        mkdir 文件夹名  
        使用这个命令可以新建一个文件夹
    3.初始化整个仓库
        git init 
        此时会在仓库建立一个隐藏的文件夹.git
    4.新建文件并添加到仓库中
        touch  文件名   此时查看状态是红色
        git add  文件名        此时再进行查看状态就为绿色
        git commit -m "说明语句"   这是为文件添加解释,此时使用git status查看状态为显示成功提交
        
 # 修改仓库中文件
    vi  文件名
    此时进入文件内，使用  i  命令进入到编辑模式，按esc则是进入到命令行模式
    下面介绍几个常用的命令，都是在命令模式下，输入 :+命令使用
          1，q 退出编辑，如果文本内容被修改过，则会报错
          2，q! 强制退出编辑，如果文本内容被修改过，会丢弃此次的修改
          3，x 退出编辑并保存
    cat 文件名
        这个命令可以查看到文件内容
    git status 
        查看我们进行的修改文件modfied
    
# 删除文件
    1.rm -rf   文件名  （本地操作）
    2.git rm   文件名  （git仓库中）
    3.git commit -m  "注释内容"
    
    
# 远程操作
    本地实现远程管理仓库，备份、实现代码的集中管理
    1.先进行克隆
      git clone  网页上面仓库地址
      此时会自行下载（需要联网），git config --list（查看信息）
    2.本地的操作，添加、删除、修改
    3.提交到GitHub中
      git push
    
# 注意问题
    在进行远程同步出现403时，解决的方案
        vi  .git/config----------->把remote="origin".
                                    url=https://用户名：密码@github.com/用户名/仓库名.git
