**初始化**

git init

**添加文件**

git add xxx yyy 可以一次性添加多个

**提交文件**

git commit -m "对这次修改的描述"

**修改后查看状态**

git status 查看修改结果

git diff xxx 查看具体修改了什么内容

**查看所有历史commit**

git log (--pretty=oneline) //括号里是简洁版

**版本回退**

在git中，用head表示当前版本，上一个版本就是HEAD^ 上上个版本就是HEAD^^  前100个版本：HEAD～100

git reset --hard HEAD^ //回到上个版本

此时再用git log会发现上次的最新版本以及不见了

但可以用commit id来恢复 前面输出过的话则直接去前面找 否则用git reflog也能找到之前的id

id只需要写前几位即可

git reset --hard 1094a



**暂存区**

隐藏目录.git为Git的版本库

版本库里存了很多东西，最重要的就是称为stage的暂存区，以及git为我们自动创建的第一个分支master，以及指向master的指针HEAD

第一步用git add实际上就是把文件修改添加到暂存区

第二步用git commit实际上就是把暂存区的所有内容提交到**当前分支**

每次修改，如果不用git add到暂存区，就不会加入到commit中



**撤销修改**

场景1：当你改乱了工作区某个文件的内容，想直接丢弃工作区的修改时，用命令 **git checkout -- file**

场景2：当你不但改乱了工作区某个文件的内容，还添加到了暂存区时，想丢弃修改，分两步，第一步用命令**git reset HEAD **，就回到了场景1，第二步按场景1操作。

场景3：已经提交了不合适的修改到版本库时，想要撤销本次提交，参考版本回退一节，不过前提是没有推送到远程库。

checkout只恢复修改过的文件，想删除未被trancked的文件使用 git clean -df



**删除文件**

一个文件commit后

先用rm命令删了这个文件

然后工作区和版本库就不一致了，现在有两个选择：

1、 从版本库中删除该文件 git rm filename 并且 git commit

2、删错了，则利用版本库恢复。git checkout -- filename



