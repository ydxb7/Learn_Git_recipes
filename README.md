# Learn Git and GitHub Recipes

This repository contains recipes for some foods I like.

This repository is used in [Udacity's Git & GitHub course](https://www.udacity.com/course/how-to-use-git-and-github--ud775)
Check out this and other courses here: https://www.udacity.com/courses/all

# My Notes

Git 和 GitHub

配置git -> tab补全，把默认编辑提交消息的editor改成sublime，修改命令行颜色等:

[https://classroom.udacity.com/courses/ud775/lessons/2980038599/concepts/33331589510923](https://classroom.udacity.com/courses/ud775/lessons/2980038599/concepts/33331589510923)

修复不同系统的换行问题：

git config --global core.autocrlf true

GitHub设置自动填写密码：

[https://classroom.udacity.com/courses/ud775/lessons/3105028581/concepts/31056889100923](https://classroom.udacity.com/courses/ud775/lessons/3105028581/concepts/31056889100923)

用SSH连接GitHub

[https://help.github.com/en/articles/connecting-to-github-with-ssh](https://help.github.com/en/articles/connecting-to-github-with-ssh)

GitHub合作：

[https://classroom.udacity.com/courses/ud775/lessons/3105028581/concepts/30736789050923](https://classroom.udacity.com/courses/ud775/lessons/3105028581/concepts/30736789050923)

加入合作者setting -> collaborators -> 输入合作者到GitHub username

<table>
  <tr>
    <td>查找文件差异</td>
    <td>diff -u file_old file_new</td>
  </tr>
  <tr>
    <td>查看每个commit</td>
    <td>git log
brach’s unreachbility 每个commit都知道他都parent commit，log可以根据parent追溯到头，同时也说明处于不同分支上到两个commit，从一个commit是访问不到另一个的</td>
  </tr>
  <tr>
    <td>只看1次提交</td>
    <td>git log -n1</td>
  </tr>
  <tr>
    <td>查看每个文件的更改情况</td>
    <td>git log --stat</td>
  </tr>
  <tr>
    <td>获得彩色的 diff 输出</td>
    <td>git config --global color.ui auto</td>
  </tr>
  <tr>
    <td>查看并回到以前的版本</td>
    <td>git checkout commit_id</td>
  </tr>
  <tr>
    <td>让HEAD回到原来的地方</td>
    <td>git checkout master</td>
  </tr>
  <tr>
    <td>初始化</td>
    <td>git init</td>
  </tr>
  <tr>
    <td>改变的文件，自从上次commit后</td>
    <td>git status</td>
  </tr>
  <tr>
    <td>缓存区文件</td>
    <td>如果没有add任何文件就是：最近commit的副本
如果add过后就是：add完还没commit的文件</td>
  </tr>
  <tr>
    <td>删除缓存区的文件（错误的add了文件）</td>
    <td>git reset file1</td>
  </tr>
  <tr>
    <td></td>
    <td></td>
  </tr>
  <tr>
    <td>2个commit的差异</td>
    <td>git diff commit_id1 commit_id2</td>
  </tr>
  <tr>
    <td>显示你所做的更改且未添加到暂存区（正在修改的文件与add到缓存区的文件的区别）</td>
    <td>git diff</td>
  </tr>
  <tr>
    <td>缓存区文件与最后一次commit文件的区别</td>
    <td>git diff --staged</td>
  </tr>
  <tr>
    <td>放弃工作目录或缓存区的所有更改，回到最近commit的内容（要小心，删了就永远回不来了）</td>
    <td>git reset --hard</td>
  </tr>
  <tr>
    <td>查看分支</td>
    <td>git branch</td>
  </tr>
  <tr>
    <td>查看分支（包括远程分支）</td>
    <td>git branch -a</td>
  </tr>
  <tr>
    <td>创建分支</td>
    <td>git branch branch_1</td>
  </tr>
  <tr>
    <td>转到branch_1</td>
    <td>git checkout branch_1</td>
  </tr>
  <tr>
    <td>创建分支并转到该分支</td>
    <td>git checkout -b branch_1
相当于依次跑了git branch branch_1 和 git checkout branch_1</td>
  </tr>
  <tr>
    <td>查看分支结构，查看master 和 branch1</td>
    <td>git log --graph --oneline master branch_1</td>
  </tr>
  <tr>
    <td>合并master和branch1</td>
    <td>git merge 还将在合并的版本中包含当前checkout的分支
git merge master branch_1
git merge branch2 branch3
git merge 始终将所有指定的分支合并到当前checkout的分支中，并为该分支新建一个提交。</td>
  </tr>
  <tr>
    <td>将 branch2 合并到 branch1 中</td>
    <td>git checkout branch1 然后 git merge branch2</td>
  </tr>
  <tr>
    <td>查看commit_id和他parent commit的区别（也就是看这个commit本身做了什么修改）</td>
    <td>git show commit_id</td>
  </tr>
  <tr>
    <td>删除branch1（只删除label）</td>
    <td>git branch -d branch_1</td>
  </tr>
  <tr>
    <td>将文件恢复到开始合并之前的状态</td>
    <td>git merge --abort</td>
  </tr>
  <tr>
    <td>merge冲突</td>
    <td>搜索<<<<确定冲突位置
这些特殊符号包含的部分（<<<<<到>>>>>的内容）就是冲突代码：
<<<<后面的是checkout的HEAD所在的代码
|||||后面的是原始版本的代码（合并的2个版本的分裂处）
=====后面的是另一个版本的代码

git add 冲突文件
git commit</td>
  </tr>
  <tr>
    <td>remote</td>
    <td></td>
  </tr>
  <tr>
    <td>查看远程仓库</td>
    <td>git remote</td>
  </tr>
  <tr>
    <td>查看远程仓库详细信息</td>
    <td>git remote -v</td>
  </tr>
  <tr>
    <td>添加远程仓库</td>
    <td>git remote add origin 远程仓库url   // 如果只有一个远程仓库可以用origin
git remote add upstream(原始远程仓库的名字) 远程仓库url </td>
  </tr>
  <tr>
    <td>推送数据</td>
    <td>git push origin(要发送更改的远程仓库) master(推送数据的本地分支)
git push origin branch1</td>
  </tr>
  <tr>
    <td>拉取数据</td>
    <td>git pull origin(要拉取的远程仓库) master(需要获取数据的本地分支)
git pull = git fetch + git merge</td>
  </tr>
  <tr>
    <td>Forking从别人的远程仓库直接copy到自己到远程仓库</td>
    <td>在要fork的别人的仓库上点击fork就行</td>
  </tr>
  <tr>
    <td>远程和本地都更新过的情况下，只把remote分支拉过来，并保持local的不动</td>
    <td>git fetch origin

然后可以用git log origin/master 查看，git log看不到，因为在不同的分支上</td>
  </tr>
  <tr>
    <td>Merge远程仓库并处理冲突</td>
    <td>git merge master origin/master</td>
  </tr>
  <tr>
    <td>pull request 合作：希望把自己的分支合并到master分支</td>
    <td>在GitHub上点击pull request，确定后会发送邮件给另一个人
https://classroom.udacity.com/courses/ud775/lessons/3105028581/concepts/31181385480923
多人合作的时候最好不要直接更新remote的master，都要通过pull request等大家都同意（处理冲突）来更新master， 如果冲突，要先把自己的分支搞定并处理好冲突（remote都pull下来，然后把master上都内容都合并到local的自己的分支上，修改local分支冲突在push自己的分支），通过修改自己的分支再pull request合并到remote的master分支。同意别人的pull request的话就在pull request的标签页点击绿色的merge按钮（灰色表示有冲突不能合并）</td>
  </tr>
  <tr>
    <td>以前的commit要修改，但是又不想修改之后的commit的结构（不要新建commit+merge，这样结构会变）</td>
    <td>git rebase</td>
  </tr>
</table>


