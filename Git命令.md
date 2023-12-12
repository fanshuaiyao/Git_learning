![image-20231211200525359](Git命令.assets/image-20231211200525359.png)

#### git基于本地仓库操作，也就是上图的存储区域

clone从远程仓库下载

publish发布自己的项目到远程仓库

git add 从工作区将文件add到比对区进行比对

git commit从比对区推送到本地仓库

当远程仓库有变化时，用pull拉取到本地仓库

当本地仓库有变化时，用push推到远程仓库

#### git --version 查看版本

![image-20231211201115377](Git命令.assets/image-20231211201115377.png)

#### 首先用git init 将文件初始化成一个git文件

![image-20231211201514569](Git命令.assets/image-20231211201514569.png)

![image-20231211201537296](Git命令.assets/image-20231211201537296.png)

#### 从远程仓库拉取仓库 git clone https://...

![image-20231211202009595](Git命令.assets/image-20231211202009595.png)

#### 从远程拉取的时候想换个名字 git clone https://... new name

![image-20231211202504834](Git命令.assets/image-20231211202504834.png)

![image-20231211202523612](Git命令.assets/image-20231211202523612.png)

#### 配置全局用户名称和全局用户邮箱

git config --global user.name fanshuaiyao

git config --global user.email 1345822123@qq.com

![image-20231211203456456](Git命令.assets/image-20231211203456456.png)

配置完成之后在此地查看

![image-20231211203329867](Git命令.assets/image-20231211203329867.png)

#### git status查看暂存区的状态

![image-20231211203955482](Git命令.assets/image-20231211203955482.png)

#### 新建一个文件a.txt，在进行状态查看，会显示未行踪

![image-20231211204347442](Git命令.assets/image-20231211204347442.png)

#### 使用git add a.txt将文件从工作区放到暂存区，再进行状态查看(git status)

![image-20231211204514479](Git命令.assets/image-20231211204514479.png)

#### 从暂存区放回工作区用git rm --cached a.txt，再查看状态（git status）就会又显示这个文件未追踪到

![image-20231211204827025](Git命令.assets/image-20231211204827025.png)

#### 也可以使用通配符来进行批量次提交 git add *.txt

![image-20231211205145548](Git命令.assets/image-20231211205145548.png)

#### 用git commit来进行文件的提交，也就是从暂存区提交到本地仓库存储区，-m后面跟备注

![image-20231211205337464](Git命令.assets/image-20231211205337464.png)

#### 再来查看状态，工作区很干净

![image-20231211205530644](Git命令.assets/image-20231211205530644.png)

#### 可以用git add . 来添加所有文件

#### 用git log查看历史记录

![image-20231211205741361](Git命令.assets/image-20231211205741361.png)

#### 可以简化查看历史记录 git log --oneline 使得版本号只显示前7个

![image-20231211205859121](Git命令.assets/image-20231211205859121.png)

#### 修改文件，status改变

![image-20231211210037758](Git命令.assets/image-20231211210037758.png)

#### 修改之后，在软件操作可以直接commit，命令行不行，先add再commit

![image-20231211210345508](Git命令.assets/image-20231211210345508.png)

#### 查看修改的历史记录

![image-20231211210446617](Git命令.assets/image-20231211210446617.png)

#### 删除文件，查看了一下暂存区的状态为

![image-20231211210802512](Git命令.assets/image-20231211210802512.png)

#### 删除也是提交，add加commit就ok

![image-20231211210910789](Git命令.assets/image-20231211210910789.png)

![image-20231211210934072](Git命令.assets/image-20231211210934072.png)

#### 如果误删除了工作区的文件，在已经提交，且删除操作没有提交的状态下，我们可以从存储区拉回来，使用git restore a.txt恢复文件

![image-20231211211415876](Git命令.assets/image-20231211211415876.png)

#### 如果提交删除也提交了，我们也可以将版本重置，使用git reset --hard （版本号）但此时历史记录丢失了删除的提交记录

![image-20231211211845185](Git命令.assets/image-20231211211845185.png)

![image-20231211212120108](Git命令.assets/image-20231211212120108.png)

#### 也可以不丢失，使用git revert 版本号（这个版本号是最新的）

![image-20231211212333573](Git命令.assets/image-20231211212333573.png)

#### 创建分支，在空仓库时没有提交的情况下，不能创建分支，当有了提交之后才能有创建分支的操作，创建分支使用git branch 分支名

![image-20231212154655824](Git命令.assets/image-20231212154655824.png)

#### 查看当前有多少个分支 git branch -v

![image-20231212154738602](Git命令.assets/image-20231212154738602.png)

#### 更改分支名称 git branch -m oldName newName

![image-20231212190647902](Git命令.assets/image-20231212190647902.png)

#### 切换分支使用git checkout user

![image-20231212155407577](Git命令.assets/image-20231212155407577.png)

#### 将创建分支和切换分支合并成一步，使用 git checkout -b 分支名

![image-20231212155546645](Git命令.assets/image-20231212155546645.png)

#### 对分支进行删除 git branch -d 分支名

![image-20231212160026119](Git命令.assets/image-20231212160026119.png)

#### 对分支进行合并，先切换到master分支上，两个分支都有同名文件，需要人工干预

![image-20231212160753139](Git命令.assets/image-20231212160753139.png)

#### 标签的创建与删除

#### git tag查看所有标签

#### 【git tag 标签名 版本号】为其版本号所对应的提交编写标签

![image-20231212163405326](Git命令.assets/image-20231212163405326.png)

#### 在查看指定历史记录时，就可以用标签来指定，不用版本号了

![image-20231212163610752](Git命令.assets/image-20231212163610752.png)

#### 删除标签 git tag -d 标签名

![image-20231212163724786](Git命令.assets/image-20231212163724786.png)

#### 本地仓库关联到远程仓库 【git remote add origin 地址】

![image-20231212183636529](Git命令.assets/image-20231212183636529.png)

#### 远程仓库变化之后，用 git pull origin 来拉取最新代码

![image-20231212181236967](Git命令.assets/image-20231212181236967.png)

#### 使用git remote remove origin删除config文件中的origin配置

![image-20231212184308176](Git命令.assets/image-20231212184308176.png)
