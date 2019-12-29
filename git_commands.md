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

但可以用commit id来恢复

id只需要写前几位即可

git reset --hard 1094a