# 记录将自己github网址上传的仓库平行复制到gitee中
首先记录下git初始化的一些过程吧
## 配置用户名及邮箱，这会在电脑中的.gitconfig中对应修改内容
```
git config --global user.name 'wjx'
git config --global user.email '2016007238@qq.com'
git config user.name  #查看邮箱用户名
git config user.email  
```
## 从github上clone到本地(以3D_vtk_software仓库为例)
打开git Bash
```
cd D:/WJX/code/     #注意是正斜杠
git clone https://github.com/wangjx520/3D_vtk_software.git 
git config --global http.proxy http://127.0.0.1:1087 #如果git下载失败，可以设置下全局网络代理，端口见设置中
git config --global --unset http.proxy #取消代理
```


## 将本地仓库上传到gitee目标仓库的master分支
### 初始化本地环境，将该项目变成可以被git管理的仓库
```
git init
```
### 添加该项目下的所有文件
```
git add .
```
### 使用如下命令将文件添加到仓库中去
```
git commit -m '本次提交的说明(说明信息为必填项，最好有意义)'
```
### gitee网址新建远程目标仓库
![gitee新建目标仓库](vx_images/550514115231171.png)


### 将本地代码库于远程仓库相关联
```
git remote add origin https://gitee.com/WANG_JIN_XIN/3D_vtk-visualization-software.git
git remote show origin  #查看远程仓库信息
git branch --vv #查看本地分支的跟踪信息
git remote remove origin #移除当前的远程仓库信息
```
### 强制把远程仓库的代码更新到当前分支上面。ps：如果仓库为空，这步可以跳过
```
git pull --rebase origin master
```
### 将本地代码推送到远程指定仓库中
版本控制系统中，分支指的将代码的不同版本以独立的线索进行管理的功能，允许开发者在同一个项目中进行不同的工作，而不会相互干扰
一个项目中有一个默认的主分支（master/main），创建新的分支时，会从当前分支（通常主分支）中分离出来，可以在分支上进行开发、修改代码，
而不会影响到其他分支的工作
```
git checkout main #切换到本地的main分支
git push origin master:main #将远程的master分支拉取到本地main分支
git push origin main #是将远程仓库中的main分支合并到本地当前main分支中，确保我的代码与远程仓库保持同步
git push -u origin master #是将本地代码推送到远程仓库，-u用于建立本地分支与远程分支之间的关联，之后推送操作可以简化为git push
git push -u origin main:master #本地的分支是main，远程的为master，这是将本地main分支推送到远程master中
```