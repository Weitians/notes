#### 创建版本库：
	$ mkdir learngit
	$ cd learngit
	$ pwd  //Users/michael/learngit

#### 初始化git仓库：
	$ git init //Initialized empty Git repository in /Users/michael/learngit/.git/

#### 添加文件到仓库：
	$ git add readme.txt
	$ git commit -m "wrote a readme file" //本次提交内容说明
	[master (root-commit) eaadf4e] wrote a readme file
	 1 file changed, 2 insertions(+)
	 create mode 100644 readme.txt
	
#### 查看仓库当前状态：
	$ git status
	On branch master
	Changes not staged for commit:
	  (use "git add <file>..." to update what will be committed)
	  (use "git checkout -- <file>..." to discard changes in working directory)
	
		modified:   readme.txt
	
	no changes added to commit (use "git add" and/or "git commit -a")
	
#### 查看修改内容：
	$ git diff readme.txt 
	diff --git a/readme.txt b/readme.txt
	index 46d49bf..9247db6 100644
	--- a/readme.txt
	+++ b/readme.txt
	@@ -1,2 +1,2 @@
	-Git is a version control system.
	+Git is a distributed version control system.
	 Git is free software.
	
#### 查看历史记录：
	$ git log
	commit a10fe95335b8de77ddd29888d79960956ed14c4b (HEAD -> master)
	Author: weitians <sankoutang@163.com>
	Date:   Wed Jun 19 10:21:54 2019 +0800
	
	    addpend GPL
	
	commit cd37b327bdc00fcba50acb1b0198e7762991df17
	Author: weitians <sankoutang@163.com>
	Date:   Wed Jun 19 10:05:22 2019 +0800
	
	    add distributed
	
	commit c5a4d5ee3e756191271dc391a74188ac6aa35bd4
	Author: weitians <sankoutang@163.com>
	Date:   Wed Jun 19 09:56:42 2019 +0800
	
	    wrote a learngit file
	
#### 版本回退：
	$ git reset --hard HEAD^
	HEAD is now at e475afc add distributed
		- HEAD指向的版本就是当前版本，因此，Git允许我们在版本的历史之间穿梭，使用命令git reset --hard commit_id。
		- 穿梭前，用git log可以查看提交历史，以便确定要回退到哪个版本。
		- 要重返未来，用git reflog查看命令历史，以便确定要回到未来的哪个版本。
		
#### 工作区（Working Directory）:
	- 电脑上的目录，仓库放置的文件夹。
	
#### 版本库（Repository) ：
	- 工作区内隐藏的目录 .git 
 Git的版本库里存了很多东西，其中最重要的就是称为stage（或者叫index）的暂存区，还有Git为我们自动创建的第一个分支master，以及指向master的一个指针叫HEAD。
![Git](https://github.com/Weitians/notes/blob/master/imges/Git_1.jpg)
第一步是用git add把文件添加进去，实际上就是把文件修改添加到暂存区；
![Git](https://github.com/Weitians/notes/blob/master/imges/Git_2.jpg)	
第二步是用git commit提交更改，实际上就是把暂存区的所有内容提交到当前分支。
![Git](https://github.com/Weitians/notes/blob/master/imges/Git_32.jpg)
因为我们创建Git版本库时，Git自动为我们创建了唯一一个master分支，所以，现在，git commit就是往master分支上提交更改，你可以简单理解为，需要提交的文件修改通通放到暂存区，然后，一次性提交暂存区的所有修改。
