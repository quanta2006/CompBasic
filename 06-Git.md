# Git
## 分布式版本控制系统

<script src="F:\Mooc\CloudData\js\"></script>
<script type="text/javascript">
 $(document).ready(function(){
      $("h2,h3,h4,h5,h6").each(function(i,item){
        // if (i == 0) continue;
        var tag = $(item).get(0).localName;
        $(item).attr("id","wow"+i);
        $("#category").append('<a class="new'+tag+'" href="#wow'+i+'">'+$(this).text()+'</a></br>');
        $(".newh2").css("margin-left",0);
        $(".newh3").css("margin-left",20);
        $(".newh4").css("margin-left",40);
        $(".newh5").css("margin-left",60);
        $(".newh6").css("margin-left",80);
      });
 });
</script>
<div id="category"></div>
<div id="main"></div>
 


### Git是什么
Git是一个版本控制系统，它可以很方便的记录你的每一次变动，而不需要每次都备份，还能让你和他人很方便的协同编辑文件，这样你每次做了什么改动，瞄一眼就一清二楚了。

### 如何安装
在Linux下面安装Git非常简单，只要运行 `apt-get install git` 就完成了。

### 创建版本库（repository）
简单的说，你可以将版本库理解为一个目录。我们用Git来管理我们的文件，所以你得告诉Git你需要它管理哪个目录下的文件，这个目录就是版本库。
```js
git init

//创建一个learnGit目录，并进入learnGit目录，创建版本库
md learnGit
cd learnGit
git init
```

--
### 添加文件到版本库中
仓库下创建的文件以及目录需要手动的提交到仓库中。提交分为两步：  
1. `git add`  
2. `git commit -m` "提交的说明"  

先创建一个文件叫做readme.txt，里面输入
```js
Git is amazing!
I love Git!
```
接着将这个readme.txt提交到仓库中：
```python
> git add readme.txt
warning: LF will be replaced by CRLF in readme.txt.
The file will have its original line endings in your working directory.

> git commit -m "add a readme file"
[master (root-commit) e7ddd65] add a readme file
warning: LF will be replaced by CRLF in readme.txt.
The file will have its original line endings in your working directory.
 1 file changed, 3 insertions(+)
 create mode 100644 readme.txt
```

--
### 工作区的状态
使用`git status`查看目前工作区的状态信息

> 将readme.md修改为
```
Git is great!
I love git!
```
> 接着使用git status命令
```python
> git status
On branch master
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

        modified:   readme.txt

no changes added to commit (use "git add" and/or "git commit -a")
```

--
### 查看文件的修改内容
虽然我们可以通过`git status`知道文件被修改了，但是我们并不了解到底修改了哪些内容。因此使用`git diff`可以知道具体的修改内容。
```python
> git diff readme.txt
diff --git a/readme.txt b/readme.txt
index 2482f69..8e882dd 100644
--- a/readme.txt
+++ b/readme.txt
@@ -1,3 +1,2 @@
-Git is amazing!
-I love Git!
-
+Git is great!
+I love git!
\ No newline at end of file
warning: LF will be replaced by CRLF in readme.txt.
The file will have its original line endings in your working directory.
```

--
### 查看整个修改过程状态
将修改过的文件进行提交
```python
> git add readme.txt
```
再来看当前工作区的状态
```python
> git status
warning: LF will be replaced by CRLF in readme.txt.
The file will have its original line endings in your working directory.
On branch master
Changes to be committed:
  (use "git reset HEAD <file>..." to unstage)

        modified:   readme.txt
```
继续提交修改后的文件
```python
> git commit -m "amazing became great"
[master warning: LF will be replaced by CRLF in readme.txt.
The file will have its original line endings in your working directory.
469dcdc] amazing became great
warning: LF will be replaced by CRLF in readme.txt.
The file will have its original line endings in your working directory.
 1 file changed, 1 insertions(+), 1 deletions(-)
```
再来看当前工作区的状态
```python
> git status
On branch master
nothing to commit, working directory clean
```

--
### 查看历史记录
`git log`命令可以查看所有的历史记录
```python
> git log
commit e4af028a493a4459fea0c0f673149281e0d11949
Author: LIYANG <liyangtom@163.com>
Date:   Tue Apr 26 16:17:58 2016 +0800

    add new line

commit 469dcdcd4de36234666885f87fa581441a834992
Author: LIYANG <liyangtom@163.com>
Date:   Tue Apr 26 16:07:00 2016 +0800

    amazing became great

commit e7ddd658bf0e5791acd07c25a56ba1c4fba1a181
Author: LIYANG <liyangtom@163.com>
Date:   Tue Apr 26 15:49:34 2016 +0800

    add a readme file
```

--
### 缩略历史记录
`git log` 命令给出了你的每一次提交，并按时间顺序依次显示，非常详细。但是有时候你只想要一个简单的结果，可以 `git log --pretty=oneline` or `git log --oneline `--graph
```
> git log --pretty=oneline
e4af028a493a4459fea0c0f673149281e0d11949 add new line
469dcdcd4de36234666885f87fa581441a834992 amazing became great
e7ddd658bf0e5791acd07c25a56ba1c4fba1a181 add a readme file
```

--
### 返回历史记录
在Git中有个指针叫做`HEAD`，`HEAD`指向哪个快照，你现在就在哪个状态。对于第N个状态的版本`HEAD~N`
```python
> git reset --hard HEAD~2
HEAD is now at e7ddd65 add a readme file
```

-- 
### 返回历史记录失败
如果现在又想重新回到`add new line`这个版本怎么办。很简单，只要知道`add new line`的`commit id`就可以了。所以你理所当然的使用`git log`查看`commit id`：
```python
> git log --pretty=oneline
469dcdcd4de36234666885f87fa581441a834992 amazing became great
e7ddd658bf0e5791acd07c25a56ba1c4fba1a181 add a readme file
```
`add new line`不见了！记住`git log`只能查看HEAD及HEAD以前的版本。

--
### 查看所有历史操作
`git reflog` 这个命令可以查看所有操作命令
```bash
> git reflog
469dcdc HEAD@{0}: reset: moving to HEAD~1
e4af028 HEAD@{3}: commit: add new line
469dcdc HEAD@{4}: commit: amazing became great
e7ddd65 HEAD@{5}: commit (initial): add a readme file
```
这时你就知道了`add new line` 的`id`了，你就可以很开心的回去了
```python
> git reset e4af028
Unstaged changes after reset:
M       readme.txt
```
