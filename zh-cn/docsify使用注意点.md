## docsify init

谨慎`docsify init`，会使得`index.html`恢复到原始内容，删除一些界面设置。

## Git恢复修改的文件

情况一、只修改了文件，没有git操作：

```
git checkout -- aaa.txt #aaa.txt是文件名
```

情况二、修改了文件，并提交到暂存区（编辑后，`git add`但没有`git commit -m ...`）

```
git log --oneline   #可以省略
git reset HEAD  #回退到当前版本
git checkout -- aaa.txt #文件名
```

情况三、修改了文件，并提交到仓库区（编辑后，`git add`和`git commit -m ...`）

```
git log --oneline   #可以省略
git reset HEAD^  #回退到上一个版本
git checkout -- aaa.txt #文件名
```

## git push使用

```
fatal: The current branch master has no upstream branch.
To push the current branch and set the remote as upstream, use

    git push --set-upstream origin master
```

首次使用`git push` 需要绑定远程的分支，需要用`--set-upstream`来绑定，之后就可以直接`git push`。

`--set-upstream`简写为`u`，即：

```
git push -u origin master
```

