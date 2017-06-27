
<span id="stash"></span>
# stash

Commed|Meaning
------|-------
git stash (save "message")|对暂存区和工作区进行缓存
git stash list|列出所有保存的缓存
git stash apply|恢复最近的缓存
git stash apply stash@{ }|恢复工作缓存
git stash pop|重新应用存储，同时立刻将其从堆栈中删除，等同于<br>`git stash apply`<br>`git stash drop stash@0`
git stash pop apply|恢复最近的缓存
git stash pop stash@{ }|恢复工作缓存
git stash drop stash@{ }|删除已储存的缓存
git stash drop stash stash@{ }|删除已储存的缓存
git stash branch branch_name|将缓存转换为分支
